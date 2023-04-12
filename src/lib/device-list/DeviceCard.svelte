<script lang="ts">
  import { onMount } from "svelte";
  import type { T_Device } from "../../types";

  export let data: T_Device;

  const { id, name, registered, lastUsed, color } = data;

  const colorExp = /\d{3}/g;
  const getLighterColor = (color: string) => {
    let colorMatch = color.match(colorExp)[0];
    const colorNum = parseInt(colorMatch);
    const newColorNum = colorNum + 5;
    return color.replace(colorMatch, `${newColorNum}`);
  };

  const getCardDimensions = () => {
    const card = document.querySelector(".device-card");
    const cardWidth = card?.clientWidth;
    const cardHeight = card?.clientHeight;
    console.log(cardWidth)
    return { cardWidth, cardHeight };
  };

  onMount(() => {
    // find some settings `width:height` ratio and then set the circles
    // numbers were found by trial and error with device sizes through
    //  the dev tools
    const { cardWidth, cardHeight } = getCardDimensions();
    const cardBefore = document.querySelector(`.card-before${id}`);
    const cardAfter = document.querySelector(`.card-after${id}`);
    console.log(cardWidth, cardHeight)

    const widthHeightRatio = Number((cardWidth / cardHeight).toFixed(2));
    console.log(widthHeightRatio)
    let top: string, left: string, bottom: string, right: string;
    let cardRatio: number = (cardWidth + cardHeight / 6);
    // there is a ratio at least at .95 where the circles touch
    // circles do not look good with landscape
    if (widthHeightRatio > .67) {
        top = '-50%';
        left = '-40%';
        bottom = '-20%';
        right = '-85%';
    } else if (widthHeightRatio > .5) {
        top = '-30%';
        left = '-40%';
        bottom = '-15%';
        right = '-85%';
    } else {
        top = '-25%';
        left = '-110%';
        bottom = '-30%';
        right = '-115%';
        cardRatio = (cardWidth + cardHeight) / 3;
    }
      
    
    // circles look good for .7 w/h ratio
    /*
      .7 {
        top: -50%;
        left: -40%;
        bottom: -20%;
        right: -85%;
        cardRatio = cardWidth + cardHeight / 6;
      }
      .5 {
        top: -30%;
        left: -40%;
        bottom: -15%;
        right: -85%;
        cardRatio = cardWidth + cardHeight / 6;
      }
      .3 {
        top: -25%;
        left: -110%;
        bottom: -30%;
        right: -115%;
        cardRatio = cardWidth + cardHeight / 3;
      }
    */
    // const cardRatio = cardWidth + cardHeight / 3;

    const psuedoCardStyle = `
      position: absolute;
      z-index: -1;
      background-color: ${getLighterColor(color)};
      border-radius: 50%;
      width: ${cardRatio}px;
      height: ${cardRatio}px;
    `;
    const cardBeforeStyle = `
      top: ${top};
      left: ${left};
    `;
    const cardAfterStyle = `
      bottom: ${bottom};
      right: ${right};
    `;
    cardBefore?.setAttribute("style", cardBeforeStyle + psuedoCardStyle);
    cardAfter?.setAttribute("style", cardAfterStyle + psuedoCardStyle);
  });
</script>

<div class="device-card" style:background-color={color}>
  <div class="card-before{id}"></div>
  <div class="card-after{id}"></div>
  <div class="icon"></div>
  <div class="name">{name}</div>
  <div class="registered">
    <div class="title">Registered:</div> 
    <div>{registered}</div>
  </div>
  <div class="last-used">
    <div class="title">Last Used:</div> 
    <div>{lastUsed}</div>
  </div>
</div>

<style lang="scss">
  .device-card {
    position: relative;
    z-index: 0;
    overflow: hidden;

    padding: 1rem;
    border-radius: .5rem;
    color: white;
    display: grid;
    gap: 1rem;
    
    .icon {
      width: 2rem;
      height: 2rem;
      background-color: white;
      border-radius: 50%;
    }

    .title {
      margin-bottom: .25rem;
      color: rgba(white, 0.5);
    }
    .name {
      font-size: 1.5rem;
      font-weight: bold;
    }

    .card-before, .card-after {
      position: absolute;
      
      border-radius: 50%;
      z-index: -1;
    }
  }
</style>