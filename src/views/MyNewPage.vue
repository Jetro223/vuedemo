<template>
  <div class="about">
    <h1>This is a NEW page</h1>

    <div class="card">
      <div class="header">
        <div class="title">Titel</div>
    	  <div class="actions">
          <button>mein button</button>

        </div>
      </div>
      <div class="body">Mein text</div>

    </div>

    <ul class="liste">
      <li>Eins</li>
      <li>Zwei</li>
    </ul>

    <ul class="liste2">
      <li>Eins</li>
      <li>Zwei</li>
    </ul>
  </div>
</template>

<style lang="scss">

$mycolor: green;

.card {
  margin: 20px;
  border: solid 1px $mycolor;

  .header {
    padding: 20px;
    background: #eaeaea;

    .title {
      font-weight: bold;
    }
  }
}

.liste {

  li {
    font-weight: bold;
  }
}


</style>
