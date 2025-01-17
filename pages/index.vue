<template>

  <div class="w-full h-[100dvh] flex flex-col justify-between">
    <div class="wrapper wrapper-vanish">
      <!-- 3) Le trou noir qui grandit -->
      <div class="hole"></div>
    </div>
    <!-- Top nav -->
    <Navbar />

    <!-- Center -->
    <div class="flex flex-col md:ml-4 p-5 md:p-10">
      <h1 class="post-anim text-[3.5rem] md:text-[9rem] font-black">Kaktuse.</h1>
      <h2 class="post-anim text-[1rem] md:text-[3rem] font-light">Innovative Web Development Solutions</h2>
    </div>

    <!-- Footer -->
    <div class="w-full flex flex-row justify-end items-end p-4 md:p-10 relative">
      <a href="mailto:contact@kaktuse.net" class="hover:underline flex items-center text-5xl md:text-4xl gap-2">
        <div class="relative">
          <Icon name="uil:envelope" />
          <span class="absolute top-0 left-0 w-4 h-4 bg-red-500 rounded-full animate-bounce"></span>
        </div>
        <h1 class="hidden md:flex">contact@kaktuse.net</h1>
      </a>
    </div>

  </div>
</template>

<style>
/* -----------------
       1) BODY NOIR + TEXTE BLANC
       ----------------- */
body {
  margin: 0;
  padding: 0;
  background: #161616;
  /* fond noir */
  color: #fff;
  /* texte blanc */
  overflow: hidden;
}

/* -----------------
       2) LE CALQUE BLANC QUI RECOVRE TOUT
       ----------------- */
.wrapper {
  position: fixed;
  inset: 0;
  /* top: 0; right: 0; bottom: 0; left: 0; */
  background: #fff;
  /* blanc */
  overflow: hidden;
  /* on coupe ce qui dépasse */
  z-index: 2;
  /* par-dessus le texte */
}

/* -----------------
       3) LE TROU NOIR QUI GRANDIT
       ----------------- */
.hole {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 0;
  height: 0;
  background: #000;
  /* noir */
  border-radius: 50%;
  /* cercle */
  animation: expand 1.2s ease-in-out forwards;
}

@keyframes expand {
  0% {
    width: 0;
    height: 0;
  }

  100% {
    /* on le rend très grand pour recouvrir tout le calque blanc */
    width: 300vh;
    height: 300vh;
  }
}

/* -----------------
       4) TEXTE : APPARAÎT APRÈS L'ANIMATION
       ----------------- */
.post-anim {
  z-index: 1;
  /* sous la wrapper (z=2), mais on va l'afficher après */
  opacity: 0;
  /* invisible au départ */
  animation: fadeInText 0.8s ease-in-out forwards 1.0s;
  /* Le "1.0s" = délai avant de lancer l'anim, 
         pour qu'il apparaisse APRES le début du trou noir 
         (vous pouvez ajuster à 1.2s si vous voulez pile à la fin). */
}

@keyframes fadeInText {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

/* -----------------
       5) OPTIONAL : FAIRE DISPARAÎTRE LE CALQUE BLANC
          après que le trou noir a tout recouvert
       ----------------- */
.wrapper-vanish {
  animation: vanish 0.8s ease-in-out 1.2s forwards;
  /* On déclenche la disparition ~en même temps que
         (ou juste après) l'expansion du trou noir */
}

@keyframes vanish {
  to {
    opacity: 0;
    pointer-events: none;
  }
}
</style>
