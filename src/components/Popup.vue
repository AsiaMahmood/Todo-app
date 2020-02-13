<template>

<!-- test -->

  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="600px"
    >
      <template v-slot:activator="{ on }">
        <v-btn v-on="on">
          إنشاء مشروع
        </v-btn>
      </template>

      <v-card>
        <v-card-title>
          أضافة مشروع جديد
        </v-card-title>

        <v-card-text>
          <v-form>
              <v-text-field v-model="title" label="العنوان" prepend-icon="folder"></v-text-field>
              <v-textarea v-model="content" label="التفاصيل" prepend-icon="edit"></v-textarea>
              <v-spacer></v-spacer>
          </v-form>
        </v-card-text>

        

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            إنشاء
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>


  

</template>

<script>
export default{

}

</script>