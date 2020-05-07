<template>
  <section class="contributions">
    <h3>Un changement de travail c'est comme un bateau qui change de cap. Nous te souhaitons d'avoir bon vent, bonne voile et surtout un phare dans cette tempête qui fait rage.</h3>
    <div class="don" v-for="contribution in contributions" :key="contribution.id">
      <p>{{contribution.text}}</p>
      <img :src="contribution.img" alt="">
    </div>
  </section>
</template>

<script>
export default {
  name: "Contributions",
  data() {
    return {
      contributions: [
        {
          id: 0,
          img: require(`@/assets/icon/anchor.svg`),
          text: "Matthieu t'offre une ancre !"
        },
        {
          id: 1,
          img: require(`@/assets/icon/boussole.svg`),
          text: "Thomas t'offre une boussole !"
        },
        {
          id: 2,
          img: require(`@/assets/icon/hat.svg`),
          text: "Nathalie t'offre une casquette !"
        },
        {
          id: 3,
          img: require(`@/assets/icon/helm.svg`),
          text: "Vincent t'offre un gouvernail !"
        },
        {
          id: 4,
          img: require(`@/assets/icon/knot.svg`),
          text: "Arthur t'offre du cordage !"
        },
        {
          id: 5,
          img: require(`@/assets/icon/lifebuoy.svg`),
          text: "Frédéric t'offre une bouée !"
        },
        {
          id: 6,
          img: require(`@/assets/icon/voilier.svg`),
          text: "Annette t'offre un voilier !"
        },
        {
          id: 7,
          img: require(`@/assets/icon/spyglass.svg`),
          text: "Loïc t'offre une longue-vue !"
        },
        {
          id: 8,
          img: require(`@/assets/icon/sailor.svg`),
          text: "Léonore t'offre un habit de marin !"
        }        
      ]
    }
  }
}
</script>

<style>
.contributions {
  max-width: 85%;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
  margin: 0 auto;
}
.contributions h3 {
  font-weight: 500;
  line-height: 1.3;
  margin-top: 0;
}
.don {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 45%;
  margin: 5px 0;
}
.don p {
  margin: 0;
}
.don img {
  width: 30px;
  height: 30px;
}

@media screen and (max-width: 600px) {
.don {
  width: 100%;
}
}
</style>