<template>
  <div class="opt-item"><!-- 钉住查词-->
    <div class="opt-item__header">
      <strong>{{ $i18n('opt_pinmode_title') }}</strong>
    </div>
    <div class="opt-item__body">
      <div class="checkbox">
        <label class="checkbox-inline">
          <input type="checkbox" v-model="pinMode.direct"> {{ $i18n('opt_mode_direct') }}
        </label>
        <label class="checkbox-inline">
          <input type="checkbox" v-model="pinMode.double"> {{ $i18n('opt_mode_double') }}
        </label>
        <label class="checkbox-inline">
          <input type="checkbox" v-model="pinMode.ctrl"> {{ $i18n('opt_mode_ctrl') }}
        </label>
      </div>
      <div class="double-click-delay" :style="{height: pinMode.double ? '44px' : '0'}">
        <div class="input-group">
          <div class="input-group-addon">{{ $i18n('opt_mode_double_click_delay') }}</div>
          <input type="number" min="1" class="form-control" v-model.number="doubleClickDelay">
          <div class="input-group-addon">{{ $i18n('opt_unit_ms') }}</div>
        </div>
      </div>
    </div>
    <div class="opt-item__description-wrap">
      <p class="opt-item__description" v-html="$i18n('opt_pinmode_description')"></p>
    </div>
  </div><!-- 钉住查词-->
</template>

<script>
export default {
  store: {
    pinMode: 'config.pinMode',
    doubleClickDelay: 'config.doubleClickDelay',
  }
}
</script>
