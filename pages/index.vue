<template>
    <main>
        <div class="container">
          <Navigasi />
            <div>
              <div class="jumbotron">
                <h1 class="text-center">Welcome to the Otahi Store</h1>
              </div>
            </div>
        </div>
    </main>
</template>

<script>
export default {
  mounted(){
    console.log(this.$supabase)
  }
}
</script>
