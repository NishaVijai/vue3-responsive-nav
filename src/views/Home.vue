<template>
  <div class="home">
    <section class="hero">
      <div class="hero-text container">
        <h1>Vue Responsive Nav Menu</h1>
        <hr />
        <h2>
          With Vue <br />
          Animations
        </h2>
        <hr />
      </div>
    </section>

    <section class="content-container">
      <h3>Content Heading</h3>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ea rem
        temporibus nostrum animi vero quisquam dolorum, illo dicta, eveniet eum
        ullam voluptate, tenetur facere expedita illum accusamus laborum numquam
        similique necessitatibus debitis laboriosam totam nisi itaque? Eligendi
        officiis aliquid quibusdam cumque esse autem, distinctio repudiandae,
        tempora dolores dolorum, quos et porro quasi praesentium aliquam
        temporibus ut sed? Eligendi dolores nulla nihil veniam esse minima
        possimus quaerat velit consequuntur! Nostrum molestiae, esse qui aut
        accusantium distinctio odio necessitatibus repellendus officia hic enim
        velit voluptates ea! Voluptatibus alias ipsam quaerat eveniet soluta
        totam earum deserunt, amet est molestiae quis omnis sunt delectus!
      </p>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Consequatur
        eligendi ratione quidem expedita. Hic eius illo vero esse excepturi
        doloremque voluptas modi, explicabo ab libero. Dolorum sunt nisi nulla
        obcaecati expedita officiis eveniet accusamus assumenda dolor dolorem
        dignissimos unde nesciunt eius qui ut repellat animi asperiores nostrum,
        aliquam, totam maiores? Mollitia, deserunt! Dolores, natus fuga
        voluptatibus fugit animi quam eius optio et aspernatur voluptas
        architecto rem cupiditate distinctio. A ab ea adipisci. Dicta
        perferendis earum sed consequatur. Voluptatum, quo veniam expedita fuga
        tempora dicta commodi, atque accusantium tenetur, veritatis facere
        quisquam! Nesciunt ea ad quo reiciendis rerum amet doloremque vel
        dignissimos voluptate nulla accusantium quasi consequuntur assumenda
        quaerat, inventore, dolor blanditiis. Dicta, labore perspiciatis
        similique, sed officia distinctio, harum exercitationem rem eligendi
        sequi corrupti officiis dolor saepe repellendus itaque assumenda
        delectus quisquam nostrum id sunt ducimus voluptates eius voluptas
        doloremque! Sit aut sunt vero quas vel qui aspernatur cumque magnam
        praesentium consequuntur minus voluptatibus, nam assumenda architecto
        harum voluptatum quam ipsam, cum commodi corporis fugiat placeat.
        Tempore aperiam est aspernatur iusto beatae vitae ut numquam, nobis
        maiores doloribus natus facilis sequi nisi laborum asperiores voluptas
        error. Nesciunt consectetur veniam quibusdam labore iure molestiae
        ratione voluptas iusto, aperiam nisi reprehenderit sequi!
      </p>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eveniet
        exercitationem labore eius commodi libero asperiores temporibus, quas
        nemo? Commodi vero beatae aspernatur fuga voluptatum sed cumque
        reprehenderit ipsam tempore nulla soluta magni, mollitia ratione
        deleniti iusto. Cumque sint voluptate error expedita saepe corporis
        exercitationem, sit similique vitae, asperiores cupiditate unde
        consectetur. Accusamus et dicta excepturi, delectus sequi ducimus
        voluptas atque. Repellendus labore quas cupiditate libero temporibus,
        reprehenderit alias ducimus iste dolor adipisci perspiciatis similique
        ratione corporis consectetur laborum ipsa nesciunt ex fugiat commodi
        iure praesentium beatae autem tempore? Culpa quisquam rem non, suscipit
        possimus ex nam eveniet officia et dolorum!
      </p>
    </section>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
};
</script>

<style lang="scss" scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;

  .hero {
    width: 100%;
    height: 100vh;
    background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/652/confectionary.png) #000;

    img {
      object-fit: cover;
      height: 100%;
      width: 100%;
    }

    .hero-text {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      color: #fff;

      h1 {
        text-transform: uppercase;
        font-size: 22px;
        padding-bottom: 4px;
      }

      h2 {
        font-size: 50px;
        @media (min-width: 550px) {
          font-size: 80px;
        }
      }

      hr:nth-child(2) {
        max-width: 365px;
        margin-bottom: 16px;
      }

      hr:nth-child(4) {
        height: 6px;
        background-color: #fff;
        border: none;
        max-width: 85px;
        margin-top: 16px;
      }
    }
  }

  .content-container {
    padding: 2rem;

    h3 {
      padding: 1rem 0 2rem;
    }

    p {
      padding-bottom: 1rem;
    }

    @media (min-width: 1140px) {
      max-width: 1140px;
    }
  }
}
</style>