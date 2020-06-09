<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-sm-6">
        <form action>
          <!-- id -->
          <div class="form-group row">
            <label for="id" class="col-sm-3 col-form-label">ID</label>
            <input
              type="text"
              class="col-sm-9 form-contorl-plaintext"
              readonly
              id="id"
              v-bind:value="taskId"
            />
          </div>
          <!-- /id -->

          <!-- title -->
          <div class="form-group row">
            <label for="title" class="col-sm-3 col-form-label">Title</label>
            <input type="text" class="col-sm-9 form-contorl-plaintext" id="title" />
          </div>
          <!-- /title -->

          <!-- content -->
          <div class="form-group row">
            <label for="content" class="col-sm-3 col-form-label">Content</label>
            <input type="text" class="col-sm-9 form-contorl-plaintext" id="content" />
          </div>
          <!-- /content -->

          <!-- person in charge -->
          <div class="form-group row">
            <label for="person-in-charge" class="col-sm-3 col-form-label">Person In Charge</label>
            <input type="text" class="col-sm-9 form-contorl-plaintext" id="person-in-charge" />
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