<style lang="less">
  .artical{
    padding: 20px 40px;
  }
  .artical .ql-toolbar.ql-snow + .ql-container.ql-snow,.ql-editor{
    min-height: 500px;
  }
  .articalDatail{
    margin:40px 20px;
  }
</style>

<template>
<div class="artical">
  <div class="articalDatail">
  iuikjkjjk
  </div>
  <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" :label-width="80">
    <FormItem label="姓名" prop="userName">
      <Input v-model="formValidate.userName"></Input>
    </FormItem>
    <FormItem label="邮件" prop="mail">
      <Input v-model="formValidate.mail" ></Input>
    </FormItem>
    <FormItem label="评论" prop="comment">
      <quill-editor
                    v-model="formValidate.comment"
                    :content="formValidate.comment"
                    :options="editorOption"
                    @change="onEditorChange($event)">
      </quill-editor>
    </FormItem>
    <FormItem>
      <Button type="primary" @click="handleSubmit('formValidate')">提交</Button>
      <Button type="ghost" @click="handleReset('formValidate')" style="margin-left: 8px">重置</Button>
    </FormItem>
  </Form>

</div>
</template>

<script>
  import 'quill/dist/quill.core.css'
  import 'quill/dist/quill.snow.css'
  import 'quill/dist/quill.bubble.css'

  import { quillEditor } from 'vue-quill-editor'
  export default {
    components: {
      quillEditor
    },
    data () {
      return {
        editorOption: {},
        formValidate: {
          userName: '',
          mail: '',
          comment:''
        },
        ruleValidate: {
          userName: [
            {required: true, message: '姓名不能为空', trigger: 'blur'}
          ],
          mail: [
            {type: 'email', message: '邮件不合法', trigger: 'blur'}
          ],
          comment:[
            {required: true,message: '评论不能为空', trigger: 'change'},
            {required: true,message: '评论不能为空', trigger: 'blur'}
          ]
        },
      }
    },
    methods: {
      onEditorChange({quill, html, text}) {
        console.log('editor change!', quill, html, text)
//        this.formValidate.comment = html
      },
      handleSubmit (name) {
            this.$refs[name].validate((valid) => {
              if (valid) {
                this.$Message.success('Success!');
                console.log(this.formValidate)
              } else {
                this.$Message.error('Fail!');
              }
            })
      },
      handleReset (name) {
        this.$refs[name].resetFields();
      }
    }
  };
</script>

<style>

</style>
