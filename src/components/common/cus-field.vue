<template>
  <span class="cus-field">
    <div class="cus-field-icon">
      <Icon v-if="iconName" :name="iconName"/>
    </div>
    <input :type="type"
        :value="value"
        @input="emitInput"
        :placeholder="placeholder"
        >
  </span>
</template>

<script>
export default {
  name: "cus-field",
  data () {
    return {

    }
  },
  props: {
    value: {},
    type: {
      type: String,
      default: 'text'
    },
    placeholder: {
      type: String
    },
    iconName: {
      type: String,
      default: ""
    }
  },
  methods: {
    emitInput (event) {
      const value = event.target.value;
      this.$emit('input', value);
    }
  }
}
</script>

<style lang="scss" scoped>
$line-height: 100%;

.cus-field {
  display: inline-block;
  border: 1px solid black;
  box-sizing: border-box;
  height: $line-height;
  line-height: $line-height;
  border-radius: .25rem;
  background: rgba($color: #dcdcdc, $alpha: 0.8);
  display: flex;
  max-height: 2rem;

  input {
    border-style: none;
    outline: none;
    background: transparent;
    line-height: $line-height;
    vertical-align: middle;
    width: 100%;
  }
}
</style>

