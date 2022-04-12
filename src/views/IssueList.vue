<template>
  <div>
    <h1>Issueリスト</h1>
    <el-button type="success" @click="getIssues()">issue取得</el-button>
    <el-row :gutter="12">
      <el-col :span="12" v-for="issue in issues" :key="issue.id">
        <el-card class="box-card" shadow="hover" style="margin: 5px 0;">
          <el-row :gutter="12">
            <el-col :span="21">{{ issue.title }}</el-col>
            <el-col :span="3">
              <el-button type="success" icon="el-icon-check" circle></el-button>
            </el-col>
          </el-row>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  import axios from 'axios';

  const client = axios.create({
    baseURL: 'https://github.com/dai-gi/todo-project',
    headers: {
      'Accept': 'application/vnd.github.v3+json',
      'Content-Type':'application/json',
    },
  })

  export default {
    name: 'IssueList',
    data() {
      return {
        issues: []
      }
    },
    methods: {
      getIssues() {
        client.get('/issues')
          .then((res) => {
            this.issues = res.data;
          })
      }
    }
  }
</script>