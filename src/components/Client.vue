<template>
<div class="admin">
    <div class="page-header">
      <br>
      <h1>Kafe TETI Firebase Vue</h1>
      <h6>Lower Ground DTETI Depan Workshop</h6>
      <br>
    </div>
    <v-carousel height=350, hide-delimiters=true>
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src">
      <div class="title">
        {{item.title}}
      </div>
    </v-carousel-item>
  </v-carousel>
    <div class="card mb-3">
      <div class="card-header">
        <h4>List Dagangan</h4>
      </div>
      <div class="card-group">
      <div class="card text-center" v-for="dagangan in dagangan" :key="dagangan.id">
        <img class="card-img-top" :src="dagangan.gambar" alt="Card image cap">
        <div class="card-body">
        <h5 class="card-title">{{ dagangan.nama }}</h5>
        <p class="card-text">Harga : Rp {{ dagangan.harga }},-
          <br>
          Stok Tersisa : {{ dagangan.kuantitas }}</p>
        </div>
      </div>
      </div>
    </div>
  </div>
</template>
<script>
import daganganRef from './../config';
  export default {
    name: 'Admin',
      firebase: {
        dagangan: daganganRef
      },
    data(){
      return {
        newDagangan: {
          nama: '',
          harga: '',
          kuantitas: '',
          gambar: ''
        },
         items: [
          {
            src: 'https://peterattiamd.com/wp-content/uploads/2014/03/toa-heftiba-106427-1440x500.jpg', title: 'Telah tersedia, Kopi Café TETI'
          },
          {
            src: 'http://www.fitnessalbum.com/wp-content/uploads/2018/04/omelete-egg-rolls-1440x500.jpg', title: 'Nasi Omelet, Mantap'
          },
          {
            src: 'https://curatedmagazine.ca/wp-content/uploads/Antojo14-1440x500.jpg', title: 'Menu baru, Rasakan kesegaran Jus Buah'
          },
          {
            src: 'https://www.free2go.com.au/-/media/racq/image/pagebanner1410x350/women-smiling-at-door-to-business-1440x500.jpg', title: 'Internship Café TETI'
          }
        ]
      }
    }
  }
</script>
<style>
.pointer {
    cursor: pointer;
  }
.title{
  position:center;
  bottom: 0px;
  background-color:rgba(0,0,0,0.5);
  color:white;
  font-size: 12em;
  padding:30px;

}

</style>