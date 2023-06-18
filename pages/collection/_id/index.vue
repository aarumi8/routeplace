<template>
    <div>
    <body class="u-body">
    <Header />
    <section class="u-clearfix u-custom-color-7 u-section-1" id="sec-6bf5">
      <div class="u-align-left u-clearfix u-sheet u-sheet-1">
        <div class="u-border-1 u-border-grey-80 u-container-style u-expanded-width u-group u-radius-10 u-shape-round u-group-1">
          <div class="u-container-layout u-container-layout-1">
            <img class="u-image u-image-round u-radius-10 u-image-1" src="../../../static/images/Screenshot2023-06-16at11.36.40PM.png" alt="" data-image-width="984" data-image-height="964">
            <p class="u-custom-font u-font-ubuntu u-text u-text-1">{{collection.collectionName}}</p>
            <p class="u-custom-font u-font-ubuntu u-text u-text-grey-40 u-text-2"> {{collection.desc}}</p>
            <div class="u-container-style u-group u-group-2">
              <div class="u-container-layout">
                <p class="u-custom-font u-font-ubuntu u-text u-text-grey-40 u-text-3">Flo​or</p>
                <p class="u-custom-font u-font-ubuntu u-text u-text-4">{{collection.floor}}</p>
              </div>
            </div>
            <div class="u-container-style u-group u-group-3">
              <div class="u-container-layout">
                <p class="u-custom-font u-font-ubuntu u-text u-text-grey-40 u-text-5">Volume</p>
                <p class="u-custom-font u-font-ubuntu u-text u-text-6">{{collection.volume}}</p>
              </div>
            </div>
            <div class="u-container-style u-group u-group-4">
              <div class="u-container-layout">
                <p class="u-custom-font u-font-ubuntu u-text u-text-grey-40 u-text-7">Items</p>
                <p class="u-custom-font u-font-ubuntu u-text u-text-8">{{collection.items}}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="u-clearfix u-custom-color-7 u-section-2" id="sec-b060">
      <div class="u-align-left u-clearfix u-sheet u-sheet-1">
        <div class="u-expanded-width u-list u-list-1">
          <div class="u-repeater u-repeater-1">
            <div v-for="item in nfts" :key="item.nftName" class="u-border-1 u-border-grey-80 u-container-style u-list-item u-radius-10 u-repeater-item u-shape-round">
              <a :href="'/collection/'+ item.collectionAddress + '/' + item.id">
              <div class="u-container-layout u-similar-container u-container-layout-1">
                <img class="u-expanded-width u-image u-image-round u-radius-10 u-image-1" src="../../../static/images/Screenshot2023-06-16at11.36.40PM.png" alt="" data-image-width="984" data-image-height="964">
                <p class="u-custom-font u-font-ubuntu u-text u-text-1">{{item.nftName}}</p>
                <p class="u-custom-font u-font-ubuntu u-text u-text-2">
                  <span class="u-text-grey-40">Price: <span class="u-text-white" style="font-weight: 700;">{{item.price}}</span>
                  </span>
                </p>
              </div>
              </a>
            </div>



          </div>
        </div>
      </div>
    </section>
    <Footer />
    </body>
    </div>
</template>

<script>
import Web3 from 'web3';

export default {
  name: 'Collection',
  data() {
    return {
      web3: null,
      collection: {},
      nfts: [],
      loading: true
    }
  },
  async created() {
    this.loading = false
    await this.getCollectionData()
    await this.getNfts()
  },
  methods: {
    async getCollectionData() {
      this.collection = {'collectionName': 'Azuki', 'desc': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.', 'floor': '$124', 'volume': '$29355', 'items': '1000'}
    },
    async getNfts() {
      this.nfts.push(
        {'nftName': 'Azuki#432', 'price': "$292", 'id': '23', 'collectionAddress': '0x20'},
        {'nftName': 'Azuki#132', 'price': "$292", 'id': '23', 'collectionAddress': '0x20'},
        {'nftName': 'Azuki#632', 'price': "$292", 'id': '23', 'collectionAddress': '0x20'},
        {'nftName': 'Azuki#32', 'price': "$292", 'id': '23', 'collectionAddress': '0x20'},

        {'nftName': 'Azuki#32', 'price': "$292", 'id': '23', 'collectionAddress': '0x20'},
      )
    },
  }
}
</script>

<style scoped>
.u-section-1 {
  background-image: none;
}

.u-section-1 .u-sheet-1 {
  min-height: 409px;
}

.u-section-1 .u-group-1 {
  margin-top: 0;
  margin-bottom: 30px;
  min-height: 379px;
}

.u-section-1 .u-container-layout-1 {
  padding: 30px 0;
}

.u-section-1 .u-image-1 {
  width: 322px;
  height: 315px;
  margin: 1px auto 0 30px;
}

.u-section-1 .u-text-1 {
  font-size: 3rem;
  font-weight: 700;
  margin: -315px 30px 0 381px;
}

.u-section-1 .u-text-2 {
  font-weight: 400;
  margin: 0 30px 0 381px;
}

.u-section-1 .u-group-2 {
  width: 107px;
  min-height: 57px;
  margin: 108px auto 0 377px;
}

.u-section-1 .u-text-3 {
  font-weight: 400;
  margin: 0;
}

.u-section-1 .u-text-4 {
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0;
}

.u-section-1 .u-group-3 {
  width: 107px;
  min-height: 57px;
  margin: -57px auto 0 485px;
}

.u-section-1 .u-text-5 {
  font-weight: 400;
  margin: 0;
}

.u-section-1 .u-text-6 {
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0;
}

.u-section-1 .u-group-4 {
  width: 107px;
  min-height: 57px;
  margin: -57px 0 0 auto;
}

.u-section-1 .u-text-7 {
  font-weight: 400;
  margin: 0;
}

.u-section-1 .u-text-8 {
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0;
}

@media (max-width: 1199px) {
  .u-section-1 .u-sheet-1 {
    min-height: 381px;
  }

  .u-section-1 .u-group-1 {
    margin-bottom: 20px;
    min-height: 361px;
  }

  .u-section-1 .u-container-layout-1 {
    padding-left: 30px;
    padding-right: 30px;
  }

  .u-section-1 .u-image-1 {
    width: 297px;
    height: 291px;
    margin-top: 0;
    margin-left: 0;
  }

  .u-section-1 .u-text-1 {
    width: auto;
    margin-top: -291px;
    margin-right: 0;
    margin-left: 329px;
  }

  .u-section-1 .u-text-2 {
    width: auto;
    margin-right: 0;
    margin-left: 329px;
    font-size: 1rem;
  }

  .u-section-1 .u-group-2 {
    min-height: 48px;
    margin-top: 61px;
    margin-left: 329px;
  }

  .u-section-1 .u-text-3 {
    font-size: 0.875rem;
  }

  .u-section-1 .u-text-4 {
    font-size: 1rem;
  }

  .u-section-1 .u-group-3 {
    min-height: 48px;
    margin-top: -49px;
    margin-right: 326px;
    margin-left: auto;
  }

  .u-section-1 .u-text-5 {
    font-size: 0.875rem;
  }

  .u-section-1 .u-text-6 {
    font-size: 1rem;
  }

  .u-section-1 .u-group-4 {
    min-height: 47px;
    margin-top: -48px;
  }

  .u-section-1 .u-text-7 {
    font-size: 0.875rem;
  }

  .u-section-1 .u-text-8 {
    font-size: 1rem;
  }
}

@media (max-width: 991px) {
  .u-section-1 .u-sheet-1 {
    min-height: 327px;
  }

  .u-section-1 .u-group-1 {
    min-height: 307px;
  }

  .u-section-1 .u-container-layout-1 {
    padding-top: 28px;
    padding-bottom: 28px;
  }

  .u-section-1 .u-image-1 {
    width: 246px;
    height: 241px;
    margin-top: 2px;
  }

  .u-section-1 .u-text-1 {
    font-size: 1.875rem;
    margin-top: -241px;
    margin-right: 176px;
    margin-left: 266px;
  }

  .u-section-1 .u-text-2 {
    font-size: 0.75rem;
    margin-left: 266px;
  }

  .u-section-1 .u-group-2 {
    margin-top: 50px;
    margin-left: 266px;
  }

  .u-section-1 .u-group-3 {
    margin-top: -48px;
    margin-right: 198px;
  }
}

@media (max-width: 767px) {
  .u-section-1 .u-sheet-1 {
    min-height: 193px;
  }

  .u-section-1 .u-group-1 {
    margin-bottom: 16px;
    min-height: 177px;
  }

  .u-section-1 .u-container-layout-1 {
    padding: 30px 10px;
  }

  .u-section-1 .u-image-1 {
    width: 153px;
    height: 150px;
    margin-top: 10px;
  }

  .u-section-1 .u-text-1 {
    font-size: 1.5rem;
    margin-top: -150px;
    margin-right: 0;
    margin-left: 170px;
  }

  .u-section-1 .u-text-2 {
    font-size: 0.625rem;
    margin-left: 170px;
  }

  .u-section-1 .u-group-2 {
    width: 61px;
    min-height: 33px;
    margin-top: 17px;
    margin-left: 171px;
  }

  .u-section-1 .u-text-3 {
    font-size: 0.625rem;
    width: auto;
  }

  .u-section-1 .u-text-4 {
    font-size: 0.625rem;
    width: auto;
  }

  .u-section-1 .u-group-3 {
    width: 69px;
    min-height: 32px;
    margin-top: -33px;
    margin-right: auto;
  }

  .u-section-1 .u-text-5 {
    font-size: 0.625rem;
  }

  .u-section-1 .u-text-6 {
    font-size: 0.625rem;
  }

  .u-section-1 .u-group-4 {
    width: 57px;
    min-height: 33px;
    margin-top: -32px;
  }

  .u-section-1 .u-text-7 {
    font-size: 0.625rem;
  }

  .u-section-1 .u-text-8 {
    font-size: 0.625rem;
  }
}

@media (max-width: 575px) {
  .u-section-1 .u-sheet-1 {
    min-height: 368px;
  }

  .u-section-1 .u-group-1 {
    margin-bottom: 15px;
    min-height: 353px;
  }

  .u-section-1 .u-container-layout-1 {
    padding-top: 10px;
    padding-bottom: 10px;
  }

  .u-section-1 .u-image-1 {
    margin-top: 0;
    margin-left: auto;
  }

  .u-section-1 .u-text-1 {
    margin-top: 9px;
    margin-left: 0;
  }

  .u-section-1 .u-text-2 {
    margin-left: 0;
  }

  .u-section-1 .u-group-2 {
    margin-top: 20px;
    margin-left: 0;
  }

  .u-section-1 .u-group-3 {
    margin-left: 62px;
  }

  .u-section-1 .u-group-4 {
    margin-top: -35px;
  }
}.u-section-2 {
  background-image: none;
}

.u-section-2 .u-sheet-1 {
  min-height: 384px;
}

.u-section-2 .u-list-1 {
  margin-bottom: 20px;
  margin-top: 0;
}

.u-section-2 .u-repeater-1 {
  grid-gap: 26px 26px;
  grid-template-columns: calc(25% - 19.5px) calc(25% - 19.5px) calc(25% - 19.5px) calc(25% - 19.5px);
  min-height: 364px;
}

.u-section-2 .u-container-layout-1 {
  padding: 10px;
}

.u-section-2 .u-image-1 {
  height: 243px;
  margin-top: 3px;
  margin-bottom: 0;
}

.u-section-2 .u-text-1 {
  font-weight: 700;
  font-size: 1.5rem;
  margin: 10px 0 0;
}

.u-section-2 .u-text-2 {
  font-weight: 400;
  margin: 23px 1px 0;
}

.u-section-2 .u-container-layout-2 {
  padding: 10px;
}

.u-section-2 .u-image-2 {
  height: 243px;
  margin-top: 3px;
  margin-bottom: 0;
}

.u-section-2 .u-text-3 {
  font-weight: 700;
  font-size: 1.5rem;
  margin: 10px 0 0;
}

.u-section-2 .u-text-4 {
  font-weight: 400;
  margin: 23px 1px 0;
}

.u-section-2 .u-container-layout-3 {
  padding: 10px;
}

.u-section-2 .u-image-3 {
  height: 243px;
  margin-top: 3px;
  margin-bottom: 0;
}

.u-section-2 .u-text-5 {
  font-weight: 700;
  font-size: 1.5rem;
  margin: 10px 0 0;
}

.u-section-2 .u-text-6 {
  font-weight: 400;
  margin: 23px 1px 0;
}

.u-section-2 .u-container-layout-4 {
  padding: 10px;
}

.u-section-2 .u-image-4 {
  height: 243px;
  margin-top: 3px;
  margin-bottom: 0;
}

.u-section-2 .u-text-7 {
  font-weight: 700;
  font-size: 1.5rem;
  margin: 10px 0 0;
}

.u-section-2 .u-text-8 {
  font-weight: 400;
  margin: 23px 1px 0;
}

@media (max-width: 1199px) {
  .u-section-2 .u-repeater-1 {
    min-height: 300px;
  }

  .u-section-2 .u-image-1 {
    height: 197px;
  }

  .u-section-2 .u-text-2 {
    margin-left: 0;
    margin-right: 0;
  }

  .u-section-2 .u-image-2 {
    height: 197px;
  }

  .u-section-2 .u-text-4 {
    margin-left: 0;
    margin-right: 0;
  }

  .u-section-2 .u-image-3 {
    height: 197px;
  }

  .u-section-2 .u-text-6 {
    margin-left: 0;
    margin-right: 0;
  }

  .u-section-2 .u-image-4 {
    height: 197px;
  }

  .u-section-2 .u-text-8 {
    margin-left: 0;
    margin-right: 0;
  }
}

@media (max-width: 991px) {
  .u-section-2 .u-repeater-1 {
    grid-template-columns: calc(50% - 13px) calc(50% - 13px);
    min-height: 919px;
  }

  .u-section-2 .u-image-1 {
    height: 312px;
  }

  .u-section-2 .u-image-2 {
    height: 312px;
  }

  .u-section-2 .u-image-3 {
    height: 312px;
  }

  .u-section-2 .u-image-4 {
    height: 312px;
  }
}

@media (max-width: 767px) {
  .u-section-2 .u-repeater-1 {
    grid-template-columns: 100%;
  }

  .u-section-2 .u-image-1 {
    height: 477px;
  }

  .u-section-2 .u-image-2 {
    height: 477px;
  }

  .u-section-2 .u-image-3 {
    height: 477px;
  }

  .u-section-2 .u-image-4 {
    height: 477px;
  }
}

@media (max-width: 575px) {
  .u-section-2 .u-image-1 {
    height: 294px;
  }

  .u-section-2 .u-image-2 {
    height: 294px;
  }

  .u-section-2 .u-image-3 {
    height: 294px;
  }

  .u-section-2 .u-image-4 {
    height: 294px;
  }
}
</style>