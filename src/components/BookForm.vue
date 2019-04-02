<template>
  <form>
    <h5 class="text-center mt-2">Generate Book Image</h5>
    <div id="canvas"></div>

    <div class="row">
      <div class="col">
        <input v-model.trim="book.title" type="text" class="form-control" placeholder="Title">
      </div>
      <div class="w-100 d-block d-sm-none"></div>
      <div class="col">
        <input v-model="book.author" type="text" class="form-control" placeholder="Author">
      </div>
      <div class="w-100 d-block d-sm-none"></div>
      <div class="col">
        <input v-model="book.coName" maxlength="36" type="text" class="form-control" placeholder="Sponsor">
      </div>
      <div class="w-100 d-block d-sm-none"></div>
      <div class="col">
        <div class="custom-file">
          <input @change="placeLogo" type="file" class="custom-file-input" id="validatedCustomFile">
          <label class="custom-file-label" for="validatedCustomFile">Choose file...</label>
        </div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <div class="input-group">
          <div class="input-group-prepend">
            <span class="input-group-text">Point 1</span>
          </div>
          <textarea
            v-model="book.point1"
            class="form-control"
            aria-label="With textarea"
            placeholder="Point 1"
          ></textarea>
        </div>
      </div>
      <div class="w-100 d-block d-sm-none"></div>
      <div class="col">
        <div class="input-group">
          <div class="input-group-prepend">
            <span class="input-group-text">Point 2</span>
          </div>
          <textarea v-model="book.point2" class="form-control" aria-label="With textarea"></textarea>
        </div>
      </div>
      <div class="w-100 d-block d-sm-none"></div>
      <div class="col">
        <div class="input-group">
          <div class="input-group-prepend">
            <span class="input-group-text">Point 3</span>
          </div>
          <textarea v-model="book.point3" class="form-control" aria-label="With textarea"></textarea>
        </div>
      </div>
      <div class="col">
        <div class="form-check">
          <input
            class="form-check-input"
            type="checkbox"
            value
            id="express"
            v-model="expressEdition"
            @change="selectExpress"
          >
          <label class="form-check-label" for="express">Express Edition</label>
        </div>
      </div>
      <div class="w-100 d-block d-sm-none"></div>
    </div>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["book", "isExpress"],
  data() {
    return {
      expressEdition: false
    };
  },
  methods: {
    placeLogo(e) {
      let fake_path = document.getElementById("validatedCustomFile").value;
      var url = URL.createObjectURL(e.target.files[0]);
      $(".custom-file-label").text(fake_path.split("\\").pop());

      this.book.imgUrl = url;
    },
    selectExpress(e) {
      this.$emit("update:isExpress", this.expressEdition);
    }
  }
};
</script>

<style lang="scss">
.custom-file-label {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding-right: 5.5rem !important;
}
</style>

