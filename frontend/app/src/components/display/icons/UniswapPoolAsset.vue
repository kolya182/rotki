<template>
  <div class="uniswap-pool-asset d-flex flex-column pa-1">
    <crypto-icon :symbol="assets[0]" size="22px" />
    <crypto-icon :symbol="assets[1]" size="22px" class="align-self-end" />
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import { TokenDetails } from '@/services/defi/types';

@Component({})
export default class UniswapPoolAsset extends Vue {
  @Prop({ required: true, type: Array, validator: value => value.length === 2 })
  assets!: TokenDetails[];
}
</script>

<style scoped lang="scss">
.uniswap-pool-asset {
  height: 48px;
  width: 48px;
  border-radius: 50%;
  background: url(~@/assets/images/defi/uniswap.svg) no-repeat 8px 32px;
  background-size: 12px 12px;

  > * {
    width: 22px;
    height: 22px;

    &:nth-child(2) {
      margin-top: -4px;
      margin-left: -4px;
    }
  }
}
</style>
