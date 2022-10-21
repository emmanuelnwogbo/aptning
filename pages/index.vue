<template>
  <div class="main">
    <div class="main__logo">
      <figure>
        <img src="@/assets/imgs/teikoicon.jpeg"/>
      </figure>
      <div class="main__logo--letters">
        <p>AptosShinobi</p>
        <p>AptosShinobi</p>
        <p>AptosShinobi</p>
      </div>
    </div>
     <div class="main__photos">
      <figure class="glitch">
        <img src="@/assets/imgs/139.png"/>
        <div class="glitch__layers">
		      <div class="glitch__layer first"></div>
		      <div class="glitch__layer first"></div>
		      <div class="glitch__layer first"></div>
	      </div>
      </figure>
      <figure class="glitch">
        <img src="@/assets/imgs/teiko2.jpeg"/>
        <div class="glitch__layers">
		      <div class="glitch__layer second"></div>
		      <div class="glitch__layer second"></div>
		      <div class="glitch__layer second"></div>
	      </div>
      </figure>
     </div>

     <div class="main__mint">
        <button class="main__mint--soon">
          minting soon
        </button>
     </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped> 
@function scaleValue($value) {
    @return calc(
      #{$value} * (clamp(350px, 100vw, 3840px) / var(--ideal-viewport-width))
    );
}

.main {
  position: relative;
  margin-top: #{scaleValue(100)};

  @media only screen and (max-width: 414px) {
    margin-top: #{scaleValue(400)};
  }

  &__logo {
    position: fixed;
    top: #{scaleValue(60)}; 
    left: #{scaleValue(100)};
    cursor: pointer;

    font-size: #{scaleValue(23)};
    font-weight: 500;
    transition: all .7s ease-in;

    animation: dropin 1.2s ease-in-out alternate;

    display: flex;
    align-items: center;

     @media only screen and (max-width: 414px) {
      font-size: #{scaleValue(60)};
      top: #{scaleValue(100)}; 
      left: #{scaleValue(70)};
     }

    & figure {
      width: #{scaleValue(35)}; 
      height: #{scaleValue(35)}; 
      overflow: hidden;
      border-radius: 100%;
      position: relative;

      margin-right: #{scaleValue(10)};

      @media only screen and (max-width: 414px) {
        width: #{scaleValue(100)}; 
        height: #{scaleValue(100)}; 
        margin-right: #{scaleValue(30)};
      }

      & img {
        width: 100%;
        height: 100%;
        object-fit: cover;

        z-index: 1;
      }
    }

    &--letters {
      margin: 0;
      line-height: 0;
      text-align: center;


      & p {
        color: #d9fff9;
        animation: glitch1 0.5s infinite;
        display: block;

        letter-spacing: #{scaleValue(1)};
        font-weight: 300;
        margin: 0;

        &:nth-child(2) {
          color: #0ef0e1;
          animation: glitch2 1.0s infinite;
        }

        &:nth-child(3) {
          color: #ff94eb;
          animation: glitch3 1.0s infinite;
        }
      }
    }
  }

  &__photos {
    display: flex;
    justify-content: center;
    align-items: center;

    & figure {
      width: #{scaleValue(400)}; 
      height: #{scaleValue(450)}; 
      overflow: hidden;
      border-radius: #{scaleValue(10)}; 
      transition: all .7s ease-in;

      margin: 0 #{scaleValue(60)}; 
      animation: cumin .7s ease-in-out alternate;


      @media only screen and (max-width: 414px) {
        width: #{scaleValue(1100)}; 
        height: #{scaleValue(1300)}; 
        
        &:nth-child(2) {
          display: none;
        }
      }

      & img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }

  &__mint {
    margin-top: #{scaleValue(100)};

    @media only screen and (max-width: 414px) {
      margin-top: #{scaleValue(180)};
    }

    display: flex;
    justify-content: center;

    &--soon {
      background: rgb(224,17,95);
      border: none;
      outline: none;
      font-weight: 400;
      font-size: #{scaleValue(22)};
      color: #fff;
      cursor: pointer;
      border-radius: 3rem;
      padding: #{scaleValue(17)} #{scaleValue(40)};

      text-transform: uppercase;

      box-shadow: 5px 47px 33px -8px rgba(224,17,95,0.27);
      -webkit-box-shadow: 5px 47px 33px -8px rgba(224,17,95,0.27);
      -moz-box-shadow: 5px 47px 33px -8px rgba(224,17,95,0.27);

      transition: all .7s ease-in;

      animation: fadeinto .7s ease-in-out alternate;

       @media only screen and (max-width: 414px) {
        font-size: #{scaleValue(70)};
        padding: #{scaleValue(55)} #{scaleValue(80)};
       }
    }
  }
}
</style>