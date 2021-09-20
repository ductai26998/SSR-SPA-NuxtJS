# SSR-SPA-NuxtJS
Note của buổi học về SSR-SPA-NuxtJS tại Sgroup 
## SSR
* Server trả về file HTML để render 
* Lần đầu tiên sẽ load nhanh hơn
* Rất tốt cho SEO
* Với nuxt chỉ cần đổi mode thành 'universal' trong nuxt.config.js để sử dụng SSR
* Không lấy được json data tròn network

## NuxtJS
* Tạo project: npx create-nuxt-app <projectName>
* Không có App.vue, muốn config gì thì vào nuxt,config.js:
  - css: Nơi chứa các đường dẫn đến file css
  - plugins: Thêm các plugin nó sẽ chạy các file plugin trong runtime
  - axios: nơi để các config của axios 
  - head: các thông tinm tương tự file index.html ở public của project Vue bình thường
* Run: yarn dev
* assets: chứa img, css, fonts, ...
* layouts: 
  - nuxt sẽ tự lấy, mặc định là file default.vue
  - VD: định nghĩa layout secret cho /about thì cần trong about.vue cần có:
  ```php
  export default {
    layout: 'secret'
  }
  ```
  - Là thư mục tạo nhiều thay đổi cho project
* pages: 
  - routing không cần route.js mà tự đặt route theo tên thư mục
  - dynamic router: đặt tên có thêm dấu gạch dưới: VD: _id thì chúng ta có thể get được id từ url
* Quy tắc đặt tên các file/folder có liên quan đến url: kebab-case 
* store: Tự import mỗi lần tao module mới 
  
##Note:
  *** Ba thư mục mà việc dặt tên ảnh hưởng quan trọng đến project: layouts, pages, store**
  *** Trong actions.js có hàm nuxtServerInit() sẽ được chạy đầu tiên tỏng lifecycle của Server Side Rendering**
  
