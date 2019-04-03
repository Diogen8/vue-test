<template>
    <div class="modal">
        <div class="modal-close">&times;</div>
        <div class="modal-inner">
            <div class="modal-body">
                <input type="text" name="call_control" placeholder="Call Control" class="modal__input">
                <input type="text" name="read" placeholder="Read" class="modal__input">
                <input type="text" name="sound" placeholder="Sound / Auto Call" class="modal__input">
                <input type="text" name="truck" placeholder="Truck" class="modal__input">
                <input type="text" name="origin" placeholder="Origin" class="modal__input">
                <input type="text" name="destination" placeholder="Destination" class="modal__input">
                <input type="text" name="pickup" placeholder="Pickup" class="modal__input">
                <input type="text" name="dh_o" placeholder="DH-O" class="modal__input">
                <input type="text" name="dh_d" placeholder="DH-D" class="modal__input">
                <input type="text" name="f_p" placeholder="F/P" class="modal__input">
                <input type="text" name="length" placeholder="Length" class="modal__input">
                <input type="text" name="weight" placeholder="Weight" class="modal__input">
                <input type="text" name="trip" placeholder="Trip" class="modal__input">
                <input type="text" name="alarm" placeholder="Alarm" class="modal__input">
                <input type="text" name="actions" placeholder="Actions" class="modal__input">
                <button>Submit</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {

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
        background-color: rgba(0,0,0,0.25);
        z-index: 999;
        justify-content: center;
        align-items: center;

        &-inner {
            background-color: white;
            padding: 40px 80px;
            max-width: 992px;
        }

        &-body {
            display: flex;
            flex-direction: column;
        }

        &__input {
            margin: 8px 0;
            font-size: 18px;
        }
    }
</style>
