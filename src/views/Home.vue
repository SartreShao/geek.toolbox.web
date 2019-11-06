<template>
  <div class="container">
    <header><h1>Geek's Toolbox</h1></header>
    <main>
      <form>
        <section>
          <h2>设计图-宽度</h2>
          <input type="number" v-model="form.design_width" />
        </section>

        <section>
          <h2>设计图-高度</h2>
          <input type="number" v-model="form.design_height" />
        </section>

        <section>
          <h2>控件-宽度(vw)</h2>
          <input type="number" v-model="form.view_width" />
        </section>

        <section>
          <h2>控件-高度(vh)</h2>
          <input type="number" v-model="form.view_height" />
        </section>
      </form>
      <button type="button" @click="clickCommit">提交</button>
      <p>{{ result }}</p>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  data() {
    return {
      result: "",
      form: {
        design_width: 1080,
        design_height: 1920,
        view_width: 0,
        view_height: 0
      }
    };
  },
  methods: {
    clickCommit: function() {
      const width = this.form.view_width / this.form.design_width;
      const height = this.form.view_height / this.form.design_height;
      this.result =
        "\n\n" +
        "width: " +
        (width * 100).toFixed(2) +
        "vw" +
        "\n" +
        "height: " +
        (height * 100).toFixed(2) +
        "vh";
    }
  }
};
</script>

<style lang="stylus" scoped>
.container {
  display flex
  flex-direction column
  padding 20px
  width 1000px
  main {
    form {
      display flex
      flex-direction row
      justify-content center
      section {
        display flex
        flex-direction column
        margin 20px
      }
    }
    p {
      white-space pre-wrap
    }
  }
}
</style>
