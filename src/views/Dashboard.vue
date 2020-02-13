<template>
  <div class="dashboard">

    <h1 class="subtitle-1 mt-4 pr-4 grey--text">Dashboard</h1>

    <v-container class="my-5">

      <v-layout row justify-start class="mb-3 mr-3">
        <v-tooltip top>
          <template v-slot:activator="{ on }">
          <v-btn text small color="grey" @click="sortBy('title')" v-on="on" > 
            <v-icon small left >folder</v-icon>
            <span class="caption text-lowercase">بالاعتماد على اسم المشروع</span> 
          </v-btn>
          </template>
          <span>ترتيب المشاريع بالاعتماد على اسم المشروع</span>
        </v-tooltip>

        <v-tooltip top>
          <template v-slot:activator="{ on }">
            <v-btn text small color="grey" @click="sortBy('person')" v-on="on" >
              <v-icon small left>person</v-icon>
              <span class="caption text-lowercase">بالاعتماد على الاسم</span> 
            </v-btn>
          </template>
          <span>ترتيب المشاريع بالاعتماد على اسم المشروع</span>
        </v-tooltip>
      </v-layout>

      <v-card flat v-for="project in projects" :key='project.title'>
        <v-layout row wrap :class="`ma-0 pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">عنوان المشروع</div>
            <div> {{project.title}} </div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">الشخص</div>
            <div>{{project.person}}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">المدة</div>
            <div>{{project.due}}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="right">
              <v-chip small :class="`${project.status} white--text my-2 caption`">{{ project.status }}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>

    </v-container>

  </div>  
</template>

<script>

export default {
  components: {
  },
  data(){
    return{
            projects: [
              { title: 'Design a new website', person: 'نور حسين', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
              { title: 'Code up the homepage', person: 'هاجر محمود', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
              { title: 'Design video thumbnails', person: 'علي موفق', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
              { title: 'Create a community forum', person: 'احمد', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
            ]
    }
  },
  methods:{
    sortBy(prop){
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }
}
</script>
<style >
.project.complete{
  border-right: 4px solid #3CD1C2;
}
.project.ongoing{
  border-right: 4px solid orange
}
.project.overdue{
  border-right: 4px solid tomato;
}

.v-chip.complete{
  background: #3cd1c2 !important;
}
.v-chip.ongoing{
  background: #ffaa2c !important;
}
.v-chip.overdue{
  background: #f83e70 !important;
}
</style>