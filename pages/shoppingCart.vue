<template>
  <div>
    <div class="page">
      <h1 class="om-oss">Dina ordrar</h1>
    </div>
    <div class="chosenBooks">
          <img src="https://secure.syndetics.com/index.aspx?isbn=9197311413/MC.GIF&client=bibivastse&type=xw10&upc=&oclc=" alt="">
          <h1>Engelsk-svensk ordbok på Agatha Christie</h1>
          <h2>Pernilla Hansén</h2>
    </div>
  </div>
</template>

<style>
.om-oss {
display: flex;
background-color:white ;
width: 450px;
justify-content: center;
border: 3px solid black;
padding: 10px;
border-radius: 10px;
margin-top: 15px;
font-size: 25px;
font-weight: bold;
}

.page{
  width: 100%;
  display: flex;
  justify-content: center;
  }

.chosenBooks{
    display: flex;
    flex-direction: column;
    font-size: 15px;
    width: 170px;
    margin: 15px;
    margin-top: 25px;
  }

.chosenBooks h1{
    font-weight: bold;
    padding: 2px;
  }

  .chosenBooks h2{
    padding: 2px;
  }

  .chosenBooks img{
    width: 170px;
    height: 210px;
    padding: 15px;
    background-color: burlywood;
    border-radius: 5px;
  }
</style>
