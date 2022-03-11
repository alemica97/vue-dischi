<template>
  <div>
      <figure>
          <img src="../assets/loader.png" alt="">
      </figure>
  </div>
</template>

<script>
export default {
    name: 'listLoader',
}
</script>

<style lang="scss" scoped>
    figure{
        width: 200px;
        height: 200px;
        & img{
            transform: rotate(0deg);
            animation: 1s linear infinite load;
            transition: all 1s;
        }
    }

    @keyframes load{
        0%{
            transform: rotate(0deg);
        }
        100%{
            transform: rotate(360deg);
        }
    }

</style>