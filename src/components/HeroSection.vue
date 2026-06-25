<template>
  <section class="hero" id="beranda">
    <div class="hero-container">

      <!-- Left Content -->
      <div class="hero-content">

        <!-- Badge -->
        <div class="hero-badges">
          <div class="trust-badge">
            <span>🛡️</span>
            Dipercaya 50.000+ Pengguna
          </div>

          <div class="cashback-preview">
            <span class="cashback-label">Cashback Hari Ini</span>
            <span class="cashback-amount">Rp 125.000</span>
            <span class="cashback-tag">🔥 Live</span>
          </div>
        </div>


        <h1>
          Belanja Lebih Hemat <br />
          <span class="shimmer-text">
            Bersama CashBaik
          </span>
        </h1>


        <p>
          Dapatkan cashback dari berbagai merchant favorit seperti
          Shopee, Tokopedia, Lazada dan marketplace populer lainnya.
        </p>


        <!-- Search Box -->
        <div class="action-box">

          <div class="input-group">
            <i class="fas fa-search search-icon"></i>

            <input
              v-model="productLink"
              type="text"
              placeholder="Cari merchant favoritmu..."
            />

          </div>


          <button 
            id="checkBtn" 
            @click="checkLink"
          >
            Cek Cashback
          </button>

        </div>


        <!-- Button -->
        <div class="hero-buttons">

          <a
            href="https://cashbaik.com/"
            class="hero-btn primary-btn"
            target="_blank"
            rel="noopener"
          >
            Kunjungi Website
          </a>


          <a
            href="https://play.google.com/store/apps/details?id=com.cashbaik.app&pcampaignid=web_share"
            class="hero-btn secondary-btn"
            target="_blank"
            rel="noopener"
          >
            Download Aplikasi
          </a>

        </div>

      </div>


      <!-- Right Illustration -->
      <div class="hero-image">

        <img 
          src="@/assets/hero.png" 
          alt="CashBaik Illustration"
        />

      </div>


    </div>
  </section>
</template>



<script setup>

import { ref } from 'vue'


const productLink = ref('')


function checkLink() {


  if (!productLink.value.trim()) {

    alert(
      'Silakan ketik nama merchant terlebih dahulu, contoh: Shopee'
    )

    return

  }


  const query = productLink.value
    .trim()
    .toLowerCase()



  const merchants = {

    shopee: 'https://shopee.co.id',

    tokopedia: 'https://www.tokopedia.com',

    lazada: 'https://www.lazada.co.id',

    blibli: 'https://www.blibli.com',

    bukalapak: 'https://www.bukalapak.com'

  }



  const found = Object.keys(merchants)
    .find(key => query.includes(key))



  if(found){

    window.open(
      merchants[found],
      '_blank'
    )

  }else{

    alert(
      `Merchant "${productLink.value}" belum tersedia. Coba: Shopee, Tokopedia, atau Lazada.`
    )

  }


}

</script>



<style scoped>


.hero-badges {

  display:flex;

  align-items:center;

  gap:12px;

  flex-wrap:wrap;

  margin-bottom:20px;

}



.trust-badge {


  background:#f1f5f9;

  padding:10px 18px;

  border-radius:30px;

  font-size:14px;

  font-weight:600;

}



.cashback-preview {


  display:flex;

  align-items:center;

  gap:8px;

  background:linear-gradient(
    135deg,
    #1b2b7a,
    #2563eb
  );


  color:white;

  padding:10px 18px;

  border-radius:30px;

  font-size:14px;

  font-weight:600;


  animation:pulse 2s infinite;

}



.cashback-label{

  opacity:.8;

  font-size:12px;

}



.cashback-amount{

  font-size:16px;

  font-weight:800;

  color:#ffd54a;

}



.cashback-tag{

  background:rgba(255,255,255,.2);

  padding:3px 8px;

  border-radius:20px;

  font-size:12px;

}



@keyframes pulse{


0%,100%{

transform:scale(1);

}


50%{

transform:scale(1.03);

}


}



@keyframes shimmer{


from{

background-position:-200% center;

}


to{

background-position:200% center;

}


}



.shimmer-text{


background:linear-gradient(

90deg,

#2563eb,

#93c5fd,

#ffffff,

#93c5fd,

#2563eb

);


background-size:200% auto;


-webkit-background-clip:text;

-webkit-text-fill-color:transparent;


animation:shimmer 3s linear infinite;


display:inline-block;


}


</style>