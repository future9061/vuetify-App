# vuetify-App


<br>


## 🎇code review

- vue에서 route 하기
  vue router 설치<br />
  vue router에서 옵션으로 history와 hash를 지정 가능, 기본은 hash 모드<br />
  ```
  createWebHashHistory() url앞에 #을 사용, 서버로 전송되지 않으므로 서버에 특별한 조치 필요하지 않음
  createWebHistory() 
  ```
  별도로 router directory 만들어서 index.js 파일 만듦<br />
  
```ruby
//index.js file
import HomeView from "@/views/HomeView.vue";
import AboutView from "@/views/AboutView.vue";
import PortfolioView from "@/views/PortfolioView.vue";
import ProjectView from "@/views/ProjectView.vue";
import GalleryView from "@/views/GalleryView.vue";
import { createRouter, createWebHashHistory } from "vue-router";

const routes = [
  { path: "/", component: HomeView },
  { path: "/about", component: AboutView },
  { path: "/portfolio", component: PortfolioView },
  { path: "/project", component: ProjectView },
  { path: "/gallery", component: GalleryView },
];

const router = createRouter({
  history: createWebHashHistory("/"), 
  routes,
});



export default router;




```
