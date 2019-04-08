<template>
  <div class="modal">
    <div class="modal-close" @click="modal_close">&times;</div>
    <div class="modal-inner">
      <div class="modal-body">
        <div class="row">
          <div class="column">
            <input type="text" name="call_control" placeholder="Call Control" class="modal__input" v-model="form.call_control">
            <input type="text" name="read" placeholder="Read" class="modal__input" v-model="form.read">
            <input type="text" name="sound" placeholder="Sound / Auto Call" class="modal__input" v-model="form.sound">
            <input type="text" name="truck" placeholder="Truck" class="modal__input" v-model="form.truck">
            <input type="text" name="origin" placeholder="Origin" class="modal__input" v-model="form.origin">
            <input type="text" name="destination" placeholder="Destination" class="modal__input" v-model="form.destination">
            <input type="text" name="pickup" placeholder="Pickup" class="modal__input" v-model="form.pickup">
            <input type="text" name="dh_o" placeholder="DH-O" class="modal__input" v-model="form.dh_o">
          </div>
          <div class="column">
            <input type="text" name="dh_d" placeholder="DH-D" class="modal__input" v-model="form.dh_d">
            <input type="text" name="f_p" placeholder="F/P" class="modal__input" v-model="form.f_p">
            <input type="text" name="length" placeholder="Length" class="modal__input" v-model="form.length">
            <input type="text" name="weight" placeholder="Weight" class="modal__input" v-model="form.weight">
            <input type="text" name="trip" placeholder="Trip" class="modal__input" v-model="form.trip">
            <input type="text" name="alarm" placeholder="Alarm" class="modal__input" v-model="form.alarm">
            <input type="text" name="actions" placeholder="Actions" class="modal__input" v-model="form.actions">
          </div>
        </div>
        <div class="row">
          <button class="modal__submit" @click="modal_submit">Submit</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  data: function () {
    return {
      form: {
        call_control: '',
        read: '',
        sound: '',
        truck: '',
        origin: '',
        destination: '',
        pickup: '',
        dh_o: '',
        dh_d: '',
        f_p: '',
        length: '',
        weight: '',
        trip: '',
        alarm: '',
        actions: ''
      }
    }
  },
  methods: {
    modal_submit: function() {
      if (!this.isFilled()) {
        this.modal_close();
      }
      else {
        this.$emit('form_save', this.form);
        this.modal_close();
      }
    },
    isFilled: function () {
      let result = false;

      for (let key in this.form) {
        if (this.form[key] != '') {
          result = true;
          break;
        }
      }

      return result;
    },
    modal_clear: function () {
      this.form = {
        call_control: '',
        read: '',
        sound: '',
        truck: '',
        origin: '',
        destination: '',
        pickup: '',
        dh_o: '',
        dh_d: '',
        f_p: '',
        length: '',
        weight: '',
        trip: '',
        alarm: '',
        actions: ''
      }
    },
    modal_close: function () {
      this.modal_clear();
      this.$emit('modal_close');
    }
  }
}
</script>

<style lang="scss" scoped>
  .modal {
    display: flex;
    flex-direction: column;
    position: fixed;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    background-color: rgba(0,0,0,0.8);
    z-index: 999;
    justify-content: center;
    align-items: center;

    &-inner {
      background-color: white;
      padding: 40px 80px;
      max-width: 992px;

      @media only screen and(max-width: 1024px) {
        padding: 0px;
        max-width: 100%;
        width: 100%;
        height: 100%;
        position: relative;
        overflow: scroll;
      }
    }

    &-body {
      display: flex;
      flex-direction: column;

      @media only screen and(max-width: 1024px) {
        padding-top: 40px;
      }
    }

    &__input {
      margin: 8px 0;
      font-size: 18px;
      padding: 4px 8px;
    }

    &-close {
      position: absolute;
      right: 20px;
      top: 20px;
      font-size: 40px;
      color: white;
      cursor: pointer;
      z-index: 1000;

      @media only screen and(max-width: 1024px) {
        color: black;
        top: 0px;
        right: 10px;
      }
    }

    &__submit {
      height: 38px;
      padding: 0 20px;
      background-color: green;
      color: white;
      text-transform: uppercase;
      font-family: sans-serif;
      border: 1px solid green;
      cursor: pointer;
      transition: all .3s ease-in-out;
      font-weight: bold;
      letter-spacing: 1.4px;
      margin-top: 20px;

      &:hover {
        background-color: transparent;
        color: green;
      }
    }

    @media only screen and(max-width: 1024px) {

      .row {
        flex-direction: column;
      }
    }
  }

  .row {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  .column {
    display: flex;
    flex-direction: column;
    padding: 0 10px;
  }
</style>
