<template>
  <el-row :gutter="20">
    <el-col :span="12">
      <el-card style="text-align: left" class="card-dark">
        <el-form ref="form" :model="form" label-width="120px">
          <el-form-item label="Activity name">
            <el-input v-model="form.name" class="input-dark"></el-input>
          </el-form-item>
          <el-form-item label="Activity zone">
            <el-select v-model="form.region" placeholder="please select your zone" value="">
              <el-option label="Zone one" value="shanghai"></el-option>
              <el-option label="Zone two" value="beijing"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="Activity time">
            <el-col :span="11">
              <el-date-picker type="date" placeholder="Pick a date" v-model="form.date1" style="width: 100%;"></el-date-picker>
            </el-col>
            <el-col class="line" :span="2">-</el-col>
            <el-col :span="11">
              <el-time-picker type="fixed-time" placeholder="Pick a time" v-model="form.date2" style="width: 100%;"></el-time-picker>
            </el-col>
          </el-form-item>
          <el-form-item label="Instant delivery">
            <el-switch v-model="form.delivery"></el-switch>
          </el-form-item>
          <el-form-item label="Activity type">
            <el-checkbox-group v-model="form.type">
              <el-checkbox label="Online activities" name="type"></el-checkbox>
              <br/>
              <el-checkbox label="Promotion activities" name="type"></el-checkbox>
              <br/>
              <el-checkbox label="Offline activities" name="type"></el-checkbox>
              <br/>
              <el-checkbox label="Simple brand exposure" name="type"></el-checkbox>
            </el-checkbox-group>
          </el-form-item>
          <el-form-item label="Resources">
            <el-radio-group v-model="form.resource">
              <el-radio label="Sponsor"></el-radio>
              <el-radio label="Venue"></el-radio>
            </el-radio-group>
          </el-form-item>
          <el-form-item label="Activity form">
            <el-input type="textarea" v-model="form.desc"></el-input>
          </el-form-item>
        </el-form>
      </el-card>
    </el-col>
    <el-col :span="12">
      ciao
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: 'UserProfile',
  data: () => ({
    form: {
      name: '',
      region: '',
      date1: '',
      date2: '',
      delivery: false,
      type: [],
      resource: '',
      desc: ''
    }
  }),
  methods: {
    save () {
      console.log('submit!')
    }
  }
}
</script>

<style>
.card-dark {
  background: #273c75;
  border: 0;
  color: #f5f6fa
}

.input-dark > .el-input__inner {
  background: #192a56;
  border-color: #192a56;
  color: #fafafa;
}

.input-dark > .el-input__inner:hover,
.input-dark > .el-input__inner:active,
.input-dark > .el-input__inner:focus {
/*
  background: #273c75;
*/
  border-color: #ED4C67;
  color: #f5f6fa
}
</style>
