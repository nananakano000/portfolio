<template>
  <base-layout>
    <v-card>
      <v-card-title>
        <h2>Skill</h2>
      </v-card-title>
      <v-card-text class="text-left">
        <v-card>
          <v-card-title><h4>使用技術</h4></v-card-title>
          <v-list>
            <v-list-item v-for="(skill, index) in skills" :key="index">
              <v-list-item-content>
                <v-list-item-title>{{ skill.title }}</v-list-item-title>
              </v-list-item-content>
              {{ skill.value }}
            </v-list-item>
          </v-list>
          <v-card-text>
            <div>その他（バックエンド）</div>
            <template v-for="(backend, index) in otherBackendSkills">
              <v-card :key="index">
                <v-card-text>
                  <div>{{ backend.title }}</div>
                  <v-chip
                    :key="index"
                    v-for="(skill, index) in backend.skills"
                    input-value="true"
                    >{{ skill }}</v-chip
                  >
                </v-card-text>
              </v-card>
            </template>
          </v-card-text>
          <v-card-text>
            <div>その他（フロントエンド）</div>
            <template v-for="(skill, index) in otherFrontendSkills">
              <v-chip :key="index" input-value="true">{{ skill }}</v-chip>
            </template>
          </v-card-text>
        </v-card>
        <v-card>
          <v-card-title><h4>資格</h4></v-card-title>
          <v-list>
            <v-list-item
              v-for="qualification in qualifications"
              :key="qualification.name"
            >
              <v-list-item-content>
                <v-list-item-title>{{ qualification.name }}</v-list-item-title>
              </v-list-item-content>
              {{ qualification.date }}
            </v-list-item>
          </v-list>
        </v-card>
      </v-card-text>
    </v-card>
  </base-layout>
</template>

<script>
import BaseLayout from "@/components/BaseLayout";

export default {
  components: {
    BaseLayout
  },
  data() {
    return {
      skills: [
        { title: "Java", value: "5年程度" },
        { title: "JavaScript", value: "1年程度" },
        { title: "PHP", value: "1年程度" }
      ],
      otherBackendSkills: [
        {
          title: "DB",
          skills: [
            "PostgreSQL",
            "MySQL",
            "DynamoDB",
            "SQL Server",
            "Oracle Database"
          ]
        },
        {
          title: "Framework",
          skills: ["Spring Framework", "Jersey", "Serverless Framework"]
        },
        {
          title: "Test",
          skills: ["JUnit", "Spock"]
        },
        {
          title: "OS",
          skills: ["Linux"]
        },
        {
          title: "ORM",
          skills: ["Sequelize", "MyBatis", "Doma"]
        },
        {
          title: "Others",
          skills: [
            "ShellScript",
            "PDF",
            "Pacemaker",
            "FFmpeg",
            "Apache",
            "Wowza Streaming Engine",
            "HTTP Live Streaming",
            "Heartbeat",
            "Tomcat",
            "AWS Lambda",
            "WebSocket",
            "Flyway"
          ]
        }
      ],
      otherFrontendSkills: [
        "Vue.js",
        "jQuery",
        "Bootstrap",
        "Vuex",
        "Vuetify.js",
        "Node.js",
        "Nuxt.js",
        "Google Maps API",
        "Thymeleaf"
      ],
      qualifications: [
        {
          name: "AWS 認定ソリューションアーキテクト – アソシエイト",
          date: "2019年05月"
        },
        { name: "OSS-DB​ ​Silver", date: "2016年03月" },
        { name: "LPIC-1", date: "2015年11月" },
        { name: "JSTQB​ Foundation​ Level", date: "2014年10月" },
        { name: "基本情報技術者", date: "2008年05月" }
      ]
    };
  }
};
</script>

<style></style>
