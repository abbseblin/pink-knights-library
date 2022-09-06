<template>
  <div>
    <div class="mainDiv">

      <div class="searchbarDiv">
    <input class="searchbar" type="text" v-model="search" placeholder="Search" />
      </div>

          <h1 class="forYou">Hand picked For You</h1>

        <div class="handPicked">

         <div class="bok">
          <div class="link">
          <a href="/karlsson"><img src="\karlsson.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="bok">
          <div class="link">
          <a href="/"><img src="\karlsson.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="bok">
          <div class="link">
          <a href="/"><img src="\karlsson.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="break">
          <!-- break -->
         </div>

         <div class="bok">
          <div class="link">
          <div class="link">
          <a href="/lejon"><img src="\lejonhjärta.jpg" alt="bok"></a>
          </div>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="bok">
          <div class="link">
          <a href="/lejon"><img src="\lejonhjärta.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="bok">
          <div class="link">
          <a href="/lejon"><img src="\lejonhjärta.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="break">
          <!-- break -->
         </div>

         <div class="bok">
          <div class="link">
          <a href="/paddington"><img src="\paddington.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="bok">
          <div class="link">
          <a href="/"><img src="\paddington.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

         <div class="bok">
          <div class="link">
          <a href="/"><img src="\paddington.jpg" alt="bok"></a>
          </div>
          <button class="korg">Lägg till i varukorg</button>
         </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
  body{
    background-color: #FFFFFF;
  }

  .mainDiv{
  }

  .searchbar{
    height: 30px;
    width: 450px;
    border: 2px solid #3b1d00;
    border-radius: 5px;
    padding: 4px;
    background-color: #ffffff;
    color: #000000;
  }

  .searchbarDiv{
    padding: 10px;
    padding-top: 20px;
    display:flex;
    justify-content: center ;
    order: 0;

  }

  .forYou{
    font-size: xx-large;
    font-family: sans-serif;
    font-style: inherit;
    font-weight: bold;
    color: #1f1235;
    padding: 10px;
  }

  .handPicked{
    display: flex;
    justify-content: space-evenly;
    flex-direction: row;
    flex-wrap: wrap;
    padding: 15px;
    gap: 30px ;
  }

  .bok{
    display: flex;
    flex-direction: column;
    justify-items: center;
    border: 3px solid black;
    padding: 10px;
    width: 250px;
    background-color: #ff6e6c;
    border-radius: 5px;
  }

  .link{
    display: flex;
    justify-content: center;
  }

  .bokImage{
    height: 200px;
  }

  .bokTitel{
    font-family: 'Times New Roman', Times, serif;
    font-size: larger;
    font-weight:600 ;
  }

  .korg{
    border: 3px solid black;
    border-radius: 15px;
    padding: 3px;
    margin: 7px;
    background-color: #ffe6e6;
    color: #1f1235;
  }

  .korg:hover{
    background-color: #fdd3d3;
  }

  .break{
    flex-basis: 100%;
    height: 0;
  }
</style>

