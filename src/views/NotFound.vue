<template>
<div id="error">
    <div>
        <h2>
    404 error
  </h2>
  <h2>
    Page Not Found
  </h2>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
#error{
    background: rgb(183, 192, 195);
    height: 80vh;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
}

#error div h2{
    color: red;
    font-size: 50px;
}
</style>