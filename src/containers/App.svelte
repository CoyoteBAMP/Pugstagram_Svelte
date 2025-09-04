<script>
    import { onMount } from 'svelte';
    import Header from '../components/Header.svelte';
    import Main from '../components/Main.svelte';
    import Sidebar from '../components/Sidebar.svelte';
    import Timeline from '../components/Timeline.svelte';

    let data = {};
    const API = 'https://kittygram-api-lg7jjtvfh.now.sh/';

    onMount(async () => {
        const response = await fetch(API);
        const result = await response.json();

        // Filtramos posts que tengan username no deseado
        const blockedUsernames = ["Thurston Waffles", "Grumpy"];
        const filteredPosts = result.posts.filter(post => !blockedUsernames.includes(post.username));

        // Guardamos en data los posts filtrados
        data = { ...result, posts: filteredPosts };
    });
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
    
    :global(body) {
        background-color: #fafafa;
        color: rgba(38, 38, 38, 0.7);
        font-family: "Lato", sans-serif;
        margin: 0;
        padding: 0;
    }
    :global(h1, h2, h3){
        margin: 0;
        padding: 0;
    }
</style>

<Header />
<Main>
    <Timeline posts={data.posts}/>
    <Sidebar {...data.user}/>
</Main>