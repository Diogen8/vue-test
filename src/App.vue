<template>
  <div class="container" :class="{'modal-shown':modalShown}">
    <div class="header">
      Post trucks
    </div>
    <div class="table">
      <div class="table__controls-wrapper">
        <div class="table__control border" @click="randomize">
          <div class="table__control-icon">
            <svg class="svg green" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
              viewBox="0 0 58 58" style="enable-background:new 0 0 58 58;" xml:space="preserve">
              <circle cx="29" cy="29" r="29"/>
              <g>
                <polygon style="fill:#FFFFFF;" points="44,29 22,44 22,29.273 22,14 	"/>
                <path style="fill:#FFFFFF;" d="M22,45c-0.16,0-0.321-0.038-0.467-0.116C21.205,44.711,21,44.371,21,44V14
                  c0-0.371,0.205-0.711,0.533-0.884c0.328-0.174,0.724-0.15,1.031,0.058l22,15C44.836,28.36,45,28.669,45,29s-0.164,0.64-0.437,0.826
                  l-22,15C22.394,44.941,22.197,45,22,45z M23,15.893v26.215L42.225,29L23,15.893z"/>
              </g>
            </svg>
          </div>
        </div>
        <div class="table__control" @click="modalShown = true">
          <div class="table__control-icon">
            <svg class="svg green" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
              width="401.994px" height="401.994px" viewBox="0 0 401.994 401.994" style="enable-background:new 0 0 401.994 401.994;"
              xml:space="preserve">
              <g>
                <path d="M394,154.175c-5.331-5.33-11.806-7.994-19.417-7.994H255.811V27.406c0-7.611-2.666-14.084-7.994-19.414
                  C242.488,2.666,236.02,0,228.398,0h-54.812c-7.612,0-14.084,2.663-19.414,7.993c-5.33,5.33-7.994,11.803-7.994,19.414v118.775
                  H27.407c-7.611,0-14.084,2.664-19.414,7.994S0,165.973,0,173.589v54.819c0,7.618,2.662,14.086,7.992,19.411
                  c5.33,5.332,11.803,7.994,19.414,7.994h118.771V374.59c0,7.611,2.664,14.089,7.994,19.417c5.33,5.325,11.802,7.987,19.414,7.987
                  h54.816c7.617,0,14.086-2.662,19.417-7.987c5.332-5.331,7.994-11.806,7.994-19.417V255.813h118.77
                  c7.618,0,14.089-2.662,19.417-7.994c5.329-5.325,7.994-11.793,7.994-19.411v-54.819C401.991,165.973,399.332,159.502,394,154.175z"
                  />
              </g>
            </svg>
          </div>
          <span class="table__control-text">
            New
          </span>
        </div>
        <div class="table__control" @click="form_clear">
          <div class="table__control-icon">
            <svg class="svg red" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
              width="348.333px" height="348.334px" viewBox="0 0 348.333 348.334" style="enable-background:new 0 0 348.333 348.334;"
              xml:space="preserve">
              <g>
                <path d="M336.559,68.611L231.016,174.165l105.543,105.549c15.699,15.705,15.699,41.145,0,56.85
                  c-7.844,7.844-18.128,11.769-28.407,11.769c-10.296,0-20.581-3.919-28.419-11.769L174.167,231.003L68.609,336.563
                  c-7.843,7.844-18.128,11.769-28.416,11.769c-10.285,0-20.563-3.919-28.413-11.769c-15.699-15.698-15.699-41.139,0-56.85
                  l105.54-105.549L11.774,68.611c-15.699-15.699-15.699-41.145,0-56.844c15.696-15.687,41.127-15.687,56.829,0l105.563,105.554
                  L279.721,11.767c15.705-15.687,41.139-15.687,56.832,0C352.258,27.466,352.258,52.912,336.559,68.611z"/>
              </g>
            </svg>
          </div>
          <span class="table__control-text">
            Delete All
          </span>
        </div>
        <div class="table__control" @click="repeat_last()">
          <div class="table__control-icon">
            <svg version="1.1" class="svg silver" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
              viewBox="0 0 20.298 20.298" style="enable-background:new 0 0 20.298 20.298; transform: rotateY(180deg);" xml:space="preserve">
              <path d="M0.952,11.102c0-0.264,0.213-0.474,0.475-0.474h2.421c0.262,0,0.475,0.21,0.475,0.474
                c0,3.211,2.615,5.826,5.827,5.826s5.827-2.615,5.827-5.826c0-3.214-2.614-5.826-5.827-5.826c-0.34,0-0.68,0.028-1.016,0.089
                v1.647c0,0.193-0.116,0.367-0.291,0.439C8.662,7.524,8.46,7.482,8.322,7.347L3.49,4.074c-0.184-0.185-0.184-0.482,0-0.667
                l4.833-3.268c0.136-0.136,0.338-0.176,0.519-0.104c0.175,0.074,0.291,0.246,0.291,0.438V1.96c0.34-0.038,0.68-0.057,1.016-0.057
                c5.071,0,9.198,4.127,9.198,9.198c0,5.07-4.127,9.197-9.198,9.197C5.079,20.299,0.952,16.172,0.952,11.102z"/>
            </svg>
          </div>
          <span class="table__control-text">
            Repost All
          </span>
        </div>
      </div>
      <table>
        <thead>
          <tr class="table__header">
              <th
                class="table__header-item"
                v-for="(value,key) in top_table.fields"
                :key="key+'_'+value"
              >{{value}}</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(single_value,key) in top_table.values"
            :key="key+'_'+single_value"
          >
            <td
              v-for="(value,key,index) in single_value"
              :key="key+'_'+value"
              :data-key="top_table.fields[index]"
            > 
              {{value}}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="table">
      <div class="table__head">
        <div class="table__results">Search results: Total: {{bottom_table.values.length}}</div>
        <div class="table__controls-wrapper">
          <div class="table__control" @click="bottom_table.values.pop()">
            <div class="table__control-icon">
              <svg version="1.1" class="svg silver" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
                viewBox="0 0 20.298 20.298" style="enable-background:new 0 0 20.298 20.298;" xml:space="preserve">
                <path d="M0.952,11.102c0-0.264,0.213-0.474,0.475-0.474h2.421c0.262,0,0.475,0.21,0.475,0.474
                  c0,3.211,2.615,5.826,5.827,5.826s5.827-2.615,5.827-5.826c0-3.214-2.614-5.826-5.827-5.826c-0.34,0-0.68,0.028-1.016,0.089
                  v1.647c0,0.193-0.116,0.367-0.291,0.439C8.662,7.524,8.46,7.482,8.322,7.347L3.49,4.074c-0.184-0.185-0.184-0.482,0-0.667
                  l4.833-3.268c0.136-0.136,0.338-0.176,0.519-0.104c0.175,0.074,0.291,0.246,0.291,0.438V1.96c0.34-0.038,0.68-0.057,1.016-0.057
                  c5.071,0,9.198,4.127,9.198,9.198c0,5.07-4.127,9.197-9.198,9.197C5.079,20.299,0.952,16.172,0.952,11.102z"/>
              </svg>
            </div>
            <span class="table__control-text">
              Undo
            </span>

          </div>
          <div class="table__control" @click="bottom_table.values=[]">
            <div class="table__control-icon">
              <svg version="1.1" class="svg red" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
                width="510px" height="510px" viewBox="0 0 510 510" style="enable-background:new 0 0 510 510;" xml:space="preserve">
                <g>
                  <path d="M255,0C114.75,0,0,114.75,0,255s114.75,255,255,255s255-114.75,255-255S395.25,0,255,0z M51,255c0-112.2,91.8-204,204-204
                    c45.9,0,89.25,15.3,124.95,43.35l-285.6,285.6C66.3,344.25,51,300.9,51,255z M255,459c-45.9,0-89.25-15.3-124.95-43.35
                    L415.65,130.05C443.7,165.75,459,209.1,459,255C459,367.2,367.2,459,255,459z"/>
                </g>
              </svg>
            </div>
            <span class="table__control-text">
              clear
            </span>
          </div>
        </div>
      </div>
      <table>
        <thead>
          <tr class="table__header">
              <th
                class="table__header-item"
                v-for="(value,key) in bottom_table.fields"
                :key="key+'_'+value"
              >{{value}}</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(single_value,key) in bottom_table.values"
            :key="key+'_'+single_value"
          >
            <td
              v-for="(value,key,index) in single_value"
              :key="key+'_'+value"
              :data-key="bottom_table.fields[index]"
            > 
              {{value}}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <modal v-if="modalShown" v-on:form_save="form_add" v-on:modal_close="modal_close"></modal>
  </div>
</template>

<script>
/* eslint-disable */
import modal from './components/Modal'

export default {
  name: 'App',
  components: {
    modal
  },
  data: function () {
    return {
      top_table: {
        fields: [
          'Call Control',
          'Read',
          'Sound / Auto Call',
          'Truck',
          'Origin',
          'Destination',
          'Pickup',
          'DH-O',
          'DH-D',
          'F/P',
          'Length',
          'Weight',
          'Trip',
          'Alarm',
          'Actions'
        ],
        values: []
      },
      bottom_table: {
        fields: [
          'Rate',
          'F',
          'Source',
          'Age',
          'Avail',
          'Truck',
          'Truck-O',
          'DH-O',
          'F/P',
          'Origin',
          'Trip',
          'Destination',
          'DH-D',
          'Truck-D',
          'Length',
          'Weight',
          'Company',
          'Phone'
        ],
        values: []
      },
      modalShown: false
    }
  },
  methods: {
    form_add: function (obj) {
      console.log('obj',obj);
      let app = this;
      app.top_table.values.push(obj);
    },
    form_clear: function () {
      this.top_table.values = [];
    },
    modal_close: function () {
      this.modalShown = false;
    },
    getRandomString: function (length) {
      let chars = 'abcdefghijklmnopqrstuvwxyz';
      let text ='';

      for( let i=0; i < length; i++ ) {
				text += chars.charAt(Math.floor(Math.random() * chars.length))
      }

			return text
    },
    repeat_last: function () {
      let arr = this.top_table.values;

      if (arr.length) {
        this.top_table.values.push(arr[arr.length - 1]);
      }
    },
    createRandomObj: function (count) {
      let obj = {}
      let result = [];

      for(let i = 0; i<count; i++) {
        obj = {
            rate: this.getRandomString(5),
            f: this.getRandomString(2),
            source: this.getRandomString(5),
            age: this.getRandomString(5),
            avail: this.getRandomString(5),
            truck: this.getRandomString(5),
            truck_O: this.getRandomString(5),
            dh_o: this.getRandomString(5),
            f_p: this.getRandomString(5),
            origin: this.getRandomString(5),
            trip: this.getRandomString(5),
            destination: this.getRandomString(5),
            dh_d: this.getRandomString(5),
            truck_d: this.getRandomString(5),
            length: this.getRandomString(5),
            weight: this.getRandomString(5),
            company: this.getRandomString(5),
            phone: this.getRandomString(5)
          };

          result.push(obj);
      }

      return result;
    },
    randomize: function () {
      setInterval(() => {
        this.bottom_table.values = this.bottom_table.values.concat(this.createRandomObj(Math.floor(Math.random() * 5 + 5)));
      },10000);
    }
  }
}
</script>

<style lang="scss">
  body {
    margin: 0;
    padding: 0;
    width: 100%;
    overflow-x: hidden;
  }

  body {
    min-height: 100vh;
    background-color: rgba(#c7c7c7,0.3);
  }
</style>


<style lang="scss" scoped>
  .container {
    &.modal-shown {
      overflow: hidden;
    }
  }

  .header {
    font-size: 22px;
    font-family: sans-serif;
    font-weight: bold;
  }

  .svg {
    &.red {
      fill: red;
    }

    &.green {
      fill: green;
    }

    &.silver {
      fill: silver;
    }
  } 

  .table {
    display: flex;
    flex-direction: column;
    margin-bottom: 100px;

    td {
      font-family: sans-serif;
    }

    tr:nth-child(odd) {
      background-color: rgba(black,0.3);
    }

    &__head {
      display: flex;
      justify-content: space-between;
      font-size: 21px;
      font-family: sans-serif;
      align-items: center;

      @media only screen and(max-width: 1024px) {
        font-size: 16px;
      }
    }

    &__header-item {
      padding: 8px 0;
      background-color: black;
      color: white;
      font-family: sans-serif;
    }

    &__controls-wrapper {
      display: flex;
      padding: 10px 0;
    }

    &__control {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0 10px; 
      opacity: 0.8;
      cursor: pointer;
      user-select: none;
      transition: all .3s ease-in-out;

      @media only screen and(max-width: 1024px) {
        
      }

      &-icon {
        width: 30px;
        height: 30px;
        margin-right: 10px;

        .svg {
          width: 100%;
          height: 100%;
        }

        @media only screen and(max-width: 1024px) {
          width: 15px;
          height: 15px;   
        }
      }

      &-text {
        font-family: sans-serif;
        font-size: 18px;
        font-weight: bold;

        @media only screen and(max-width: 1024px) {
          font-size: 12px;
        }
      }

      &:hover {
        opacity: 1;
      }

      &.border {
        &::after {
          content: '';
          display: block;
          height: 100%;
          background-color: black;
          width: 3px;
        }
      }
    }
  }

   @media only screen and(max-width: 1024px) {
     //table magic
      table, thead, tbody, th, td, tr {
        display: block;
      }

      thead tr {
        position: absolute;
        top: -9999px;
        left: -9999px;
      }

      tr {
        margin: 0 0 1rem 0;
      }
      
      td {
        display: flex;
        align-items: center;
        border: none;
        border-bottom: 1px solid rgba(blue,0.3);
        position: relative;
        padding-left: 50%;
        min-height: 24px;

        &:first-of-type {
          border-top: 1px solid rgba(blue,0.3);
        }
      }

      td:before {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        left: 6px;
        width: 30%;
        padding-right: 10px;
        white-space: nowrap;
        border-right: 1px solid rgba(blue,0.3);
        height: 100%;
        display: flex;
        align-items: center;
      }

      td:before { 
        content: attr(data-key); 
      }
    }
</style>
