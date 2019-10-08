<template>
  <div id="app" class="container">
    <template>
      <h1 v-if="radio">{{ msgR }}</h1>
      <h1 v-if="check">{{ msgC }}</h1>
      <h1 v-if="table">{{ msgT }}</h1>
      <hr>
      <template v-if="radio">
        <div class="form-group" v-for="(inp, index) in answersR" :key="index">
          <input type="radio" class="form-check-input" :value="inp" v-model="a"> {{ inp }}
        </div>
      </template>
      <template v-if="check">
        <div class="form-group" v-for="(inp, indexx) in answersR" :key="indexx">
          <input type="checkbox" :value="inp" v-model="b"> {{ inp }}
        </div>
      </template>
      <hr>
      <button class="btn btn-success" v-if="radio" @click.prevent="radioAns">Ответить</button>
      <button class="btn btn-success" v-if="check" @click.prevent="checkAns">Ответить</button>
      </template>
      <table v-if="table" class="table table-bordered">
        <tr>
          <td>
            Вопрос
          </td>
          <td>
            Ваш ответ
          </td>
        </tr>
        <tr>
          <td>
            {{ msgR }}
          </td>
          <td>
            {{ a }}
          </td>
        </tr>
        <tr>
          <td>
            {{ msgC }}
          </td>
          <td>
            {{ b }}
          </td>
        </tr>
      </table>
  </div>
</template>

<script>
import List from './components/list'
export default {
  name: 'app',
  data() {
    return {
      msgR: 'Какой тег задаёт ссылку?',
      msgC: 'Какие теги являются строчными',
      msgT: 'Итого',
      radio: true,
      check: false,
      table: false,
      answersR: ['div', 'span', 'a', 'table'],
      answersC: ['div', 'span', 'a', 'table'],
      a: '',
      b: []
    }
  },
  methods: {
    radioAns() {
      this.radio = false;
      this.check = true;
    },
    checkAns() {
      this.check = false;
      this.table = true;
    }
  }
}
</script>

<style>

</style>
