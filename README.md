ActivityModule           : 생성시 엑티비티를 인자로 받고 엑티비티를 제공하고 처리자들(프리젠터) 를 제공한다.  데거 컴포넌트에 이용된다.
ApplicationModule      : 생성시 어플리케이션을 주입받고 어플리케이션을 제공한다.   데거 컴포넌트에 이용된다.
ServiceModule           : 생성시 서비스를 주입받는다.   데거 컴포넌트에 이용된다.


ApplicationComponent : 데거가 스캔해야 되는 어플리케이션 모듈을을 정의 하고
                                 주입받아야 되는 어플리케이션을 정의 하여 데거에 이용 되도록 한다.

ActivityComponent      :  데거가 스캔해야 되는 어플리케이션컴포넌트(ApplicationComponent) 과 엑티비티모듈(ActivityModule )를 정의 하고
                                  주입 받아야 되는 엑티비티를 정의하여 데거에 이용 되도록 한다.
                                 1개의 모듈에 4개의 제공자가 있고 주입 엑티비티가 4개라면
                                 아래와 같이 각 엑티비티에서 4개의 기능을 하용하게 될 수 있는건 컴포넌트가 아래와 같은 엑티비티와 기능제공자에 대한
                                 연결고리를 제공하기 때문이다.

                                  ActivityModuel 기능 제공자1  --> ActivityComponent <-- 사용될 엑티비티 1
                                  ActivityModuel 기능 제공자2  --> ActivityComponent <-- 사용될 엑티비티 2
                                  ActivityModuel 기능 제공자3  --> ActivityComponent <-- 사용될 엑티비티 3
                                  ActivityModuel 기능 제공자4  --> ActivityComponent <-- 사용될 엑티비티 4

                                  ActivityModuel 기능 제공자2  --> ActivityComponent <--  사용될 엑티비티 1
                                  ActivityModuel 기능 제공자3  --> ActivityComponent <--  사용될 엑티비티 2
                                  ActivityModuel 기능 제공자4  --> ActivityComponent <--  사용될 엑티비티 3
                                  ActivityModuel 기능 제공자1  --> ActivityComponent <--  사용될 엑티비티 4

                                  ActivityModuel 기능 제공자3  --> ActivityComponent <--  사용될 엑티비티 1
                                  ActivityModuel 기능 제공자4  --> ActivityComponent <--  사용될 엑티비티 2
                                  ActivityModuel 기능 제공자1  --> ActivityComponent <--  사용될 엑티비티 3
                                  ActivityModuel 기능 제공자2  --> ActivityComponent <--  사용될 엑티비티 4

                                  ActivityModuel 기능 제공자4  --> ActivityComponent <--  사용될 엑티비티 1
                                  ActivityModuel 기능 제공자1  --> ActivityComponent <--  사용될 엑티비티 2
                                  ActivityModuel 기능 제공자2  --> ActivityComponent <--  사용될 엑티비티 3
                                  ActivityModuel 기능 제공자3  --> ActivityComponent <--  사용될 엑티비티 4

ServiceComponent      :  데거가 스캔해야 되는 어플리케이션컴포넌트(ApplicationComponent) 과 서비스 모듈을 정의하고
                                  주입 받아야 되는 동기화 서비스를 정의 하여 데거에 이용되도록 한다.

이제 데거에 필요한 어플리케이션 / 엑티비티 /

MvApp.java               : 어플리케이션이 onCreate 될때 데거 컴포넌트변수 에
                               빌더를 통해서   ApplicateionModule 에 정의된 제공자 + MvApp 자체를 인자 값으로 빌드 된다.
                               이컴포넌트변수는 BaseActivity 에서 사용될 수 있다.

BaseActivity              : 모든 엑티비티가 상속받는 최상위 엑티비티로
                               베이스엑티비티 onCreate 될때 데거 컴포넌트 변수에
                               MvApp 에서 제공하는 컴포는트 + ActivityModule 을 인자값으로 빌드 된다.





# Android MVP Architecture: Sample App
[![Mindorks](https://img.shields.io/badge/mindorks-opensource-blue.svg)](https://mindorks.com/open-source-projects)
[![Mindorks Community](https://img.shields.io/badge/join-community-blue.svg)](https://mindorks.com/join-community)

This repository contains a detailed sample app that implements MVP architecture using Dagger2, GreenDao, RxJava, FastAndroidNetworking, PlaceHolderView and AndroidDebugDatabase
<p align="center">
  <img src="https://janishar.github.io/images/mvp-app-pics/mvp-login.png" width="250">
  <img src="https://janishar.github.io/images/mvp-app-pics/main-view.png" width="250">
  <img src="https://janishar.github.io/gifs/mvp-app.gif" width="250">
</p>
<br>
<p align="center">
  <img src="https://janishar.github.io/images/mvp-app-pics/mvp-drawer.png" width="200">
  <img src="https://janishar.github.io/images/mvp-app-pics/mvp-rating.png" width="200">
  <img src="https://janishar.github.io/images/mvp-app-pics/mvp-feed.png" width="200">
  <img src="https://janishar.github.io/images/mvp-app-pics/mvp-empty-state.png" width="200">
</p>
<br>
<br>

# Architecture Blueprint
![Blueprint](https://janishar.github.io/images/mvp-app-pics/mvp-arch.png)
<br>

# Project Structure
![Structure](https://janishar.github.io/images/mvp-app-pics/mvp-project-structure-diagram.png)
<br>

# Read the below listed articles. They describe the MVP concepts and the Project structure.
1. [MVP: Part 1](https://blog.mindorks.com/essential-guide-for-designing-your-android-app-architecture-mvp-part-1-74efaf1cda40#.lkml1yggq)
2. [MVP: Part 2](https://blog.mindorks.com/essential-guide-for-designing-your-android-app-architecture-mvp-part-2-b2ac6f3f9637#.dge0wl8rl)
3. [MVP: Part 3](https://blog.mindorks.com/essential-guide-for-designing-your-android-app-architecture-mvp-part-3-dialog-viewpager-and-7bdfab86aabb)
4. [Extension with Interactors and Repositories](https://blog.mindorks.com/android-mvp-architecture-extension-with-interactors-and-repositories-bd4b51972339)

#### The app has following packages:
1. **data**: It contains all the data accessing and manipulating components.
2. **di**: Dependency providing classes using Dagger2.
3. **ui**: View classes along with their corresponding Presenters.
4. **service**: Services for the application.
5. **utils**: Utility classes.

#### Classes have been designed in such a way that it could be inherited and maximize the code reuse.

### Library reference resources:
1. RxJava2: https://github.com/amitshekhariitbhu/RxJava2-Android-Samples
2. Dagger2: https://github.com/MindorksOpenSource/android-dagger2-example
3. FastAndroidNetworking: https://github.com/amitshekhariitbhu/Fast-Android-Networking
4. PlaceHolderView: https://github.com/janishar/PlaceHolderView
5. AndroidDebugDatabase: https://github.com/amitshekhariitbhu/Android-Debug-Database
6. Calligraphy: https://github.com/chrisjenx/Calligraphy
7. GreenDao: http://greenrobot.org/greendao/
8. ButterKnife: http://jakewharton.github.io/butterknife/

### Concept reference resources:
1. [Introduction to Dagger 2: Part 1](https://blog.mindorks.com/introduction-to-dagger-2-using-dependency-injection-in-android-part-1-223289c2a01b#.ki6nt86l6)
2. [Introduction to Dagger 2: Part 2](https://blog.mindorks.com/introduction-to-dagger-2-using-dependency-injection-in-android-part-2-b55857911bcd#.mkpzyk8sa)
3. [Android Dagger2: Critical things to know before you implement](https://blog.mindorks.com/android-dagger2-critical-things-to-know-before-you-implement-275663aecc3e#.bskiz1879)
4. [The Best Android Networking Library for Fast and Easy Networking](https://blog.mindorks.com/simple-and-fast-android-networking-19ed860d1455#.cyzrve85o)
5. [RxJava + Fast Android Networking](https://blog.mindorks.com/rxjava-fast-android-networking-6e3d90ee4387#.7hjoex22m)
6. [Migrating from RxJava 1.0 to RxJava 2.0 and Learn RxJava by Examples](https://blog.mindorks.com/migrating-from-rxjava1-to-rxjava2-5dac0a94b4aa#.3lg46kora)
7. [Android Tinder Swipe View Example](https://blog.mindorks.com/android-tinder-swipe-view-example-3eca9b0d4794#.u7i7jbbvy)
8. [Debugging Android Databases And Shared Preferences In The Easiest Way](https://blog.mindorks.com/debugging-android-databases-and-shared-preferences-in-the-easiest-way-e5f705dfc06b#.pxw0hvnws)
9. [RxJava Anatomy: What is RxJava, how RxJava is designed, and how RxJava works.](https://blog.mindorks.com/rxjava-anatomy-what-is-rxjava-how-rxjava-is-designed-and-how-rxjava-works-d357b3aca586)
10. [Powerful Android ORM: greenDAO 3 Tutorial](https://mindorks.com/blog/powerful-android-orm-greendao-3-tutorial)

### Playstore App of Mindorks build on this MVP architecture
[Correctify: An English Editing and Learning app](https://play.google.com/store/apps/details?id=com.mindorks.correctify)

### Looking for MVVM Architecture - [Check here](https://github.com/MindorksOpenSource/android-mvvm-architecture)

### Looking for Kotlin MVP Architecture - [Check here](https://github.com/MindorksOpenSource/android-kotlin-mvp-architecture)

### Mindorks open source projects
[Check out Mindorks awesome open source projects here](https://mindorks.com/open-source-projects)

### How do I use this project?
This is a boilerplate project aimed to help bootstrap new Android MVP Applications. Feel free to fork this application or use [AndroidStarters](http://androidstarters.com/) to create new app using this boilerplate.

### License
```
   Copyright (C) 2017 MINDORKS NEXTGEN PRIVATE LIMITED

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```

### Contributing to Android MVP Architecture
All pull requests are welcome, make sure to follow the [contribution guidelines](CONTRIBUTING.md)
when you submit pull request.
