# vuetify-App


<br>


## 🎇code review

- **vue에서 route 하기**
  vue router 설치<br />
  vue router에서 옵션으로 history와 hash를 지정 가능, 기본은 hash 모드<br />
  ```
  *createWebHashHistory()
   url이 바뀌면 페이지 전체 리소스 로딩 없이 이동한다.
   url 앞에 #을 사용해서 페이지를 식별해 라우팅을 처리하는 방식, 기본 설정이다!
   history와 달리 서버로 post 요청 안하기 때문에 특별한 서버 처리 불필요.
   hash 값이 변경되면 브라우저는 자동으로 해당 해시 값으로 스크롤 or 뒤로 가기, 앞으로 가기 기능이 가능
   -> 마치 리액트의 navigate(-1) 같이 기능하는 듯하다.
   검색엔진최적화(SEO)에 악영향을 미치기 때문에 history mode가 더 권장된다.
   
 

  *createWebHistory()
   url이 바뀌면 전체 리소스 로딩 후 해당 페이지 이동한다.
   url에 #이 붙지 않아 보기엔 좋으나 사용자가 직접 url을 적어 서버에 post 요청을 보내면 404 오류 발생!!!!
   ->내가 만든 앱에 서버가 없고 서버 설정도 없음..
   포괄적인 대체 경로를 추가하면 문제 해결 가능 


  -> hash와 history의 가장 큰 차이점은 페이지 이동 시 리소스 로딩의 하나?, url로 서버에 post 요청의 하나?인 듯 하다 
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
