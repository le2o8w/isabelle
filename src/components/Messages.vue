<template>
  <section>
    <div class="message" v-for="message in messages" :key="message.id">
      <!-- Quote left -->
      <svg class="top" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="116" height="104" viewBox="0 0 116 104">
        <g transform="translate(7 -19.844)">
          <path d="M0,72.092v42.857H42.857V72.092H14.286A28.6,28.6,0,0,1,42.857,43.521V29.235A42.9,42.9,0,0,0,0,72.092Z" transform="translate(0 0)"/>
          <path d="M276.739,43.521V29.235a42.9,42.9,0,0,0-42.857,42.857v42.857h42.857V72.092H248.168a28.6,28.6,0,0,1,28.571-28.571Z" transform="translate(-176.739 0)"/>
        </g>
      </svg>
      <!-- Message -->
      <div class="text">
        <p v-html="message.text"></p>
        <span class="signature">{{message.name}}</span>
      </div>
      <!-- Quote right -->
      <svg class="bottom" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="116" height="104" viewBox="0 0 116 104">
        <g transform="translate(107 124.341) rotate(180)">
          <path d="M0,72.092v42.857H42.857V72.092H14.286A28.6,28.6,0,0,1,42.857,43.521V29.235A42.9,42.9,0,0,0,0,72.092Z" transform="translate(0 0)"/>
          <path d="M276.739,43.521V29.235a42.9,42.9,0,0,0-42.857,42.857v42.857h42.857V72.092H248.168a28.6,28.6,0,0,1,28.571-28.571Z" transform="translate(-176.739 0)"/>
        </g>
      </svg>
    </div>    

    <!-- Retour accueil -->
    <div class="return">
      <a @click="endOfMessages">Rejouer le diaporama</a> 
    </div>
  </section>
</template>

<script>
  export default {
    name: "Messages",
    data() {
      return {
        messages : [
          {
            id: 0,
            name: "Loïc",
            text: "Merci de m'avoir guidé dans ce Fidustage, tu as été une super chef de projet durant ces quelques mois et j'ai énormément apprécié travailler avec toi ! Je te souhaite pleins de bonnes choses pour la suite !"
          },
          {
            id: 1,
            name: "Annette",
            text: "Merci Isabelle pour ta volonté, ta tenacité, ton écoute, ton support, ta sollicitude ... et j'en passe (la liste est bien trop longue :) ).<br>J'ai vraiment adoré travailler avec toi: tu as su t'adapter, rassembler et mettre de la cohésion dans cette équipe, des qualités apparemment pas corporate à Fidu.<br>Tu es une chef de projet au top et tu vas laisser un grand vide. Snif !!!! :(<br>Je ne doute pas que tu vas cartonner dans ton nouveau job et je te souhaite le meilleur pour la suite!!!<br>Merciiiiiiiiiiiiiiiiiiiiiiiiiii ! "
          },
          {
            id: 2,
            name: "Nathalie",
            text: "Isabelle,<br>Je te souhaite tout «  le bonheur du monde » dans ta nouvelle boîte.<br>Nos Fiduconversations vont me manquer …<br>En espérant se faire rapidement une fidubouffe/engiebouffe !<br>Bon vent ! Et n’aie pas de regrets !<br>Bises"
          }, 
          {
            id: 3,
            name: "Léo",
            text: "Merci Isabelle de m'avoir rassurée et encouragée dans mon premier poste de développeur ! Tu mets la barre très haut pour tes successeurs :) C'était un plaisir de travailler avec toi.<br>J'espère que ton nouveau job t'apportera l'épanouissement et la stabilité que Fiducial n'aura pas su t'offrir.<br> On a hâte de voir des photos de tes chaussures de sécu et ton casque de chantier !"
          },
          {
            id: 4,
            name: "Vincent",
            text: "en vertue de la (case du jeu de l') oi(e) du 7/5/2019, la carte de départ n'ayant pas pu être signée par tous les participants, son départ est repoussé puisque ladite carte fait office d'attestation ex-employeur pour avoir le droit de se déplacer aillurs<br>et donc si ca permet de la garder, je signe pas ;-)"
          }
        ]
      }
    },
    methods: {
      endOfMessages() {
        this.$emit("endOfMessages", true);
      }
    }
  }
</script>

<style>
.message {
  position: relative;
  max-width: 80%;
  margin: 20px auto;
  background: #4e647b;
  border-radius: 5px;
  padding: 30px 0;
  box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

.message:hover {
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
}

.text{
  width: 85%;
  margin: 0 auto;
}
p {
  line-height: 1.6;
  margin-bottom: 0;  
}
.signature {
  display: block;
  text-align: right;
  font-family: "Bluu Next";
  font-style: italic;
  letter-spacing: 1px;
  font-size: 1.5em;
  padding-right: 10px;
}

svg {
  width: 30px;
  height: 25px;
  fill: #fff;
}
svg.top {
  position: absolute;
  left: 15px;
  top: 15px
}

svg.bottom {
  position: absolute;
  right: 15px;
  bottom: 15px
}
.return {
  max-width: 80%;
  margin: 20px auto;
  display: flex;
  justify-content: flex-end;
}
.return a{
  display: block;
  cursor: pointer;
  background: #4e647b;
  border-radius: 5px;
  padding: 15px 20px;
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);

}
.return a:hover {
  box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
}

@media screen and (max-width: 800px) {
  svg {
    width: 20px;
    height: 15px;
  }
  .signature {
    margin-bottom: 10px;
  }
  .return a{
    width: 100%;
    text-align: center;
  }
}
</style>