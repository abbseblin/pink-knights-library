<template>
  <div class="helpPage">
    <div class="divHelp">
      <img style="width:500px" src="bibliotekknappar.png" alt="">
      <h1>Vad gör dessa knappar?</h1>
      <ul class="knappList">
        <li><b>"hem": </b>Denna knapp tar dig till förstasidan</li>
        <li><b>"Hjälp": </b>Denna knapp tar dig till hjälpsidan (Där du befinner dig nu)</li>
        <li><b>"Vårat team": </b>Här ser du vilka som jobbar i biblioteket</li>
        <li><b>"varukorg": </b>Med denna knapp kommer du till varukorgen där du ser dina ordrar</li>
      </ul>
    </div>

    <div class="divHelp">
      <h1>Hur gör du en order?</h1>
      <ol>
        <li><b>1.</b> Antingen söker du på en bok i sökfältet eller scrollar efter bok en som du gillar</li>
        <li><b>2.</b> Klicka på boken du vill välja</li>
        <li><b>3.</b> Nu kan du se detaljerna om boken. Om du klickar på den gröna knappen så läggs boken till i varukorgen</li>
      </ol>
    </div>
  </div>
</template>

<style scoped>
.helpPage{
  display: flex;
  flex-direction: row;
  justify-content:center;
}
.divHelp{
  padding: 15px;
  margin: 30px;
  background-color: burlywood;
  width: 530px;
  border-radius: 10px;
}
.knappList{

}
h1{
  font-size: 30px;
}
li{
  margin-top: 10px;
  font-size: larger;
}
</style>
