<style>
  .Share {
    border: 1px solid rgba(219, 219, 219, 1);
    border-radius: 4px;
    background-color: white;
    margin: 0 0 2em 0;
    width: 300px;
    height: 80px;
    position: absolute;
    top: 300px;
    left: 30%;
    z-index: 9;
    padding: 1em;
  }
  .Share-head {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .Share-head h2 {
    font-size: 16px;
  }
  .icon-button {
    border: none;
    background: transparent;
    cursor: pointer;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .Share-content a {
    display: flex;
    align-items: center;
    text-decoration: none;
    color: black;
    font-size: 14px;
    margin: 2em 0 0 0;
  }
  .Share-content i {
    color: #3b5998;
    margin: 0 0.5em 0 0;
    font-size: 20px;
  }
</style>

<div class="Share">
  <div class="Share-head">
    <h2>Compartir</h2>
    <button class="icon-button" on:click>
      <i class="fas fa-times-circle"></i>
    </button>
  </div>
  <div class="Share-content">
    <a href="https://www.facebook.com/sharer.php?&u=https://pugstagram.com" target="_blank">
      <i class="fab fa-facebook-square"></i>
      Compartir en Facebook
    </a>
  </div>
</div>