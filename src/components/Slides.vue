<template>
  <article class="slides">
    <transition name="slide" mode="out-in">
      <figure v-for="i in [currentIndex]" :key="i">
        <figcaption>{{current.text}}</figcaption>
        <img :src="current.img" />
      </figure>
    </transition> 
    <button class="prev" @click="prev" v-if="currentIndex > 0">&#10094;</button>
    <button class="next" @click="next">&#10095;</button>
  </article>
</template>

<script>
export default {
  name: "Slides",
  data() {
    return{
      data: [
        {
          text: 'Ton départ nous attriste...',
          img: require('@/assets/img/sad.gif')
        },
        {
          text: 'Nous formions une super équipe.',
          img: require('@/assets/img/team.gif')
        }, 
        {
          text: 'Tu as su briller lors des réunions et présenter notre travail sous son meilleur jour (même quand tout n\'était pas très au point.)...',
          img: require('@/assets/img/meeting.gif')
        }, 
        {
          text: '... et tu nous as épargné les séances de travail où notre présence n\'était clairement pas indispensable.',
          img: require('@/assets/img/meetingpizza.gif')
        }, 
        {
          text: 'Tu as géré les difficultés avec panache...',
          img: require('@/assets/img/complaint.gif')
        }, 
        {
          text: '... même quand tes interlocuteurs étaient peu coopératifs...',
          img: require('@/assets/img/support.gif')
        }, 
        {
          text: 'Tu nous as toujours encouragées et tu as eu confiance en nous.',
          img: require('@/assets/img/believe.gif')
        }, 
        {
          text: 'Dans les bons moments...',
          img: require('@/assets/img/champagne.gif')
        }, 
        {
          text: '... comme dans les coups durs...',
          img: require('@/assets/img/tired.gif')
        }, 
        {
          text: '... tu as donné le maximum pour l\'équipe et nos projets...',
          img: require('@/assets/img/work.gif')
        },
        {
          text: '... tu nous as fait rire...',
          img: require('@/assets/img/laugh.gif')
        },
        {
          text: '... et tu as rendu nos journées de travail plus agréables !',
          img: require('@/assets/img/happy.gif')
        },
        {
          text: 'Tes nouveaux collègues ont de la chance de t\'accueillir !',
          img: require('@/assets/img/applause.gif')
        }, 
        {
          text: 'On se verra bientôt autour d\'un verre...',
          img: require('@/assets/img/mojitos.gif')
        },
        {
          text: '... peut-être même qu\'on poussera la chansonnette !',
          img: require('@/assets/img/karaoke.gif')
        }
      ],
      currentIndex: 0
    };
  },

  methods: {
    next: function() {
      this.currentIndex += 1;
      if (this.currentIndex === this.data.length) {
        this.$emit("endOfSlides", false);
      }
    },
    prev: function() {
      if (this.currentIndex - 1 < 0) {
        return;
      } else {
        this.currentIndex -= 1;
      }
    }
  },

  computed: {
    current: function() {
      return this.data[Math.abs(this.currentIndex) % this.data.length];
    },
  }
};
</script>

<style>

.slides {
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 600px;
}

figure {
  text-align: center;
}

img {
  width: 100%;
  max-width: 400px;
}

figcaption {
  margin: 1em 0;
  font-size: 1.5em;
  line-height: 1.5;
}

.prev, .next {
  position: absolute;
  top: 50%;
  width: auto;
  padding: 0.5em 1em;
  background: transparent;
  color: #fff;
  font-weight: bold;
  font-size: 1.5em;
  border: none;
  transition: 0.7s ease;
  user-select: none;
  outline: none;
  cursor: pointer;
}
.prev {
  left: 30%;
}
.next {
  right: 30%;
}

.prev:hover, .next:hover {
  background-color: rgba(255,255,255,0.5);
}

.slide-leave-active,
.slide-enter-active {
  transition: all 0.4s ease-in-out;
  pointer-events: none;
}
.slide-enter {
  transform: translate(100%, 0);
}
.slide-leave-to {
  transform: translate(-100%, 0);
}

@media screen and (max-width: 1400px) {
  .prev {
    left: 20%;
  }
  .next {
    right: 20%;
  }
}
@media screen and (max-width: 800px) {
  .prev {
    left: 10%;
  }
  .next {
    right: 10%;
  }
}
@media screen and (max-width: 600px) {
  .slides {
    max-width: 300px;
  }
  .prev, .next {
    font-size: 1.25em;
  }
  .prev {
    left: 0;
  }
  .next {
    right: 0;
  }
}
</style>
