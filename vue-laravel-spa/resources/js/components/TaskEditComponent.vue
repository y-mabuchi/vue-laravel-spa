<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-sm-6">
        <form v-on:submit.prevent="submit">
          <!-- id -->
          <div class="form-group row">
            <label for="id" class="col-sm-3 col-form-label">ID</label>
            <input
              type="text"
              class="col-sm-9 form-contorl-plaintext"
              readonly
              id="id"
              v-model="task.id"
            />
          </div>
          <!-- /id -->

          <!-- title -->
          <div class="form-group row">
            <label for="title" class="col-sm-3 col-form-label">Title</label>
            <input
              type="text"
              class="col-sm-9 form-contorl-plaintext"
              id="title"
              v-model="task.title"
            />
          </div>
          <!-- /title -->

          <!-- content -->
          <div class="form-group row">
            <label for="content" class="col-sm-3 col-form-label">Content</label>
            <input
              type="text"
              class="col-sm-9 form-contorl-plaintext"
              id="content"
              v-model="task.content"
            />
          </div>
          <!-- /content -->

          <!-- person in charge -->
          <div class="form-group row">
            <label for="person-in-charge" class="col-sm-3 col-form-label">Person In Charge</label>
            <input
              type="text"
              class="col-sm-9 form-contorl-plaintext"
              id="person-in-charge"
              v-model="task.person_in_charge"
            />
          </div>
          <!-- /person in charge -->

          <!-- submit -->
          <button type="submit" class="btn btn-primary">Submit</button>
          <!-- /submit -->
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // uriのパラメータを取得
  props: {
    taskId: String
  },
  // template内で使うオブジェクトの宣言
  data: function() {
    return {
      task: {}
    };
  },
  // 関数定義
  methods: {
    // APIからtaskIdのタスクを取得して、dataに代入
    getTask() {
      axios.get("/api/tasks/" + this.taskId).then(res => {
        this.task = res.data;
      });
    },
    // submitボタンが押されたら、APIにPUTしてリダイレクト
    submit() {
      axios.put("/api/tasks/" + this.taskId, this.task).then(res => {
        this.$router.push({ name: "task.list" });
      });
    }
  },
  // templateが呼び出されたときの動作
  mounted() {
    this.getTask();
  }
};
</script>