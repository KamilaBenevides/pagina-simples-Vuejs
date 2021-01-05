<template>
    <footer class="contact footer">
    <div class="container py-5">
      <div class="row py-0" id="textos">
        <div class="col-lg-3 col-md-1 mb-4 mb-lg-0">
          <h6 class="text-uppercase font-weight-bold mb-4">elpis</h6>
          <ul class="list-unstyled mb-0">
            <li class="mb-2"><a href="#" class="text-muted">Política de privacidade</a></li>
            <li class="mb-2"><a href="#" class="text-muted">Fale conosco</a></li>
            <li class="mb-2"><a href="#" class="text-muted">Termo de uso</a></li>
          </ul>
        </div>
        <div class="col-lg-3 col-md-1 mb-4 mb-lg-0">
          <h6 class="text-uppercase font-weight-bold mb-4">Siga nosso projeto</h6>
          <ul class="list-unstyled mb-0">
            <img class="d-inline-block align-top" href="#" src="../assets/facebook.svg" alt="" width="50" height="24">
            <img class="d-inline-block align-top" href="#" src="../assets/twitter.svg" alt="" width="50" height="24" >
            <img class="d-inline-block align-top" href="#" src="../assets/instagram.svg" alt="" width="50" height="24">
          </ul>
        </div>
      </div>
    </div>

  </footer>
</template>
<script>
export default {
    
}
</script>
<style scoped>
.container{
  background-color: darkred;
}
#textos{
  color: #f0eeee;
}
.text-muted{
  color: #f0eeee;
}
.contact{
  padding-inline-end: 0px;
}
.footer {
    position:absolute;
    bottom:0;
    width:100%;
}
</style>