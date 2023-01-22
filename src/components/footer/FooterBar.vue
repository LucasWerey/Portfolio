<template>
  <div class="footerCompo">
    <footer>
      <div class="Text">
        <p></p>
        <p>Created by <a href="https://www.linkedin.com/in/lucaswerey/" target="_blank">Lucas WEREY</a> @2023</p>
       <p></p>
      </div>
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
  margin-top: -60px;
}


.footerCompo {
  width: 100%;
}

.Text {
  width: 90%;
  display: flex;
  justify-content: space-between;
}

p,
a {
  font-size: 20px;
  color: #fff;
  font-weight: bold;
}

a {
  text-underline-offset: 5px;
}

</style>