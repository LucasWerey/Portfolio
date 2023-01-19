<template>
  <div class="footerCompo">
    <div class="separator"></div>
    <footer>
      <p>Ce portfolio a été réalisé par Lucas WEREY @2023</p>
    </footer>
  </div>
</template>
  

<style scoped>
footer {
  background-color: #FDC830;
  text-align: center;
  width: 100%;
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.separator {
  background-color: rgb(255, 255, 255);
  width: 25%;
  height: 2px;
  margin-top: 150px;
}

.footerCompo {
  display: flex;
  flex-direction: column;
  width: 100%;
}

p {
  font-size: 20px;
  color: #fff;
  font-weight: bold;
}
</style>