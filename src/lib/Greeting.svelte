<section id="greeting">
  <div class="introduction">
    <div class="hello">Hello,</div>
    <div class="name">Grumpy Wizard</div>

  </div>
  <div class="profile">
    <img src="https://placekitten.com/50/50" alt="Kitten" />
  </div>
</section>

<style lang="scss">
  #greeting {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 4rem 1rem 0 1rem;
  }

  .introduction {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
  }

  .hello {
    font-size: 1.5rem;
    font-weight: 600;
    color: rgba(white, 0.5);
  }

  .name {
    font-size: 1.5rem;
    font-weight: 700;
    color: white;
  }

  .profile {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .profile img {
    width: 50px;
    height: 50px;
    border-radius: .5rem;
  }
</style>