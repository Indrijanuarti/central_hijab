<template>
<main>
    <div class="container">
        <Navigasi />
        <div>
            <div class="jumbotron">
                <product/>
            </div>
                <div class="row">
                <div class="col-md-4" v-for="item in items" :key="item.id">
                    <div class="card mb-3">
                    <div class="card-header">
                        <img :src="item.foto" width="100%"> 
                    </div>
                    <div class="card-body">
                        <h4>{{ item.nama }}</h4>
                        <h4>Rp{{ item.harga }}</h4>
                    </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</main>
</template>

<script>
export default {
    data() {
    return {
        items: '',
        }
    },
    mounted() {
    this.ambilData()
    },
    methods: {
    async ambilData() {
        const { data, error } = await this.$supabase
        .from('tb_produk')
        .select()
        if(data) this.items = data
        if(error) console.log(error)
        }
    }
}
</script>
