<template>
  <section id="bemutatkozas">
    <div class="container">
      <div class="container bemutatkozas">
        <h1 class="display-1 animation_text">&zwnj;</h1>
        <h1 class="display-2">Vendégház</h1>
        <p class="lead">
          Balatonfüred szívében családias vendégházunk szeretettel vár
          mindenkit, aki egy kis kikapcsolódásra vágyik a Balaton északi
          partján. A hatalmas kertben grill és tűzrakóhely, pajta és kerti tó
          várja a pihenésre vágyókat.
        </p>

        <div class="dog_images">
          <img
            class="kutyabarat_img_1"
            src="../assets/images/kutyabarat/kutyabarat_img_1.png"
            style="width: 100%"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { gsap } from "../../node_modules/gsap";
import { RoughEase } from "gsap/EasePack";
import { TextPlugin } from "gsap/TextPlugin";

gsap.registerPlugin(TextPlugin, RoughEase);

export default {
  name: "MainTemplate",
  mounted() {
    const words = ["Kutyabarát", "Gyerekbarát", "Fecskebarát"];

    let masterTL = gsap.timeline({ repeat: -1 });

    words.forEach((word) => {
      let tl = gsap.timeline({ repeat: 1, yoyo: true, repeatDelay: 1 });
      tl.to(".animation_text", { duration: 1, text: word });
      masterTL.add(tl);
    });
  },
};
</script>

