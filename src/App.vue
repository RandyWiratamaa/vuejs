<template>
  <div id="global-loader">
      <img src="assets/images/loader.svg" class="loader-img" alt="Loader">
  </div>
  
  <div class="page">
    <div class="page-main">
      <HeaderLayout />
      <SidebarLayout />
    </div>
    <div class="main-content app-content mt-0">
        <div class="side-app">
            <div class="main-container container-fluid">
                <div class="page-header">
                    <h1 class="page-title">Dashboard 01</h1>
                    <div>
                        <ol class="breadcrumb">
                            <li class="breadcrumb-item"><a href="javascript:void(0)">Home</a></li>
                            <li class="breadcrumb-item active" aria-current="page">Dashboard 01</li>
                        </ol>
                    </div>
                </div>
                <div class="row">
                    <div class="col-lg-12 col-md-12 col-sm-12 col-xl-12">
                      <router-view/>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <SidebarRight />
    <FooterLayout />        
  </div>
  <a href="#top" id="back-to-top"><i class="fa fa-angle-up"></i></a>
</template>


<script>
import HeaderLayout from "@/components/HeaderLayout.vue";
import SidebarLayout from "@/components/SidebarLayout.vue";
import SidebarRight from "@/components/SidebarRight.vue";
import FooterLayout from "@/components/FooterLayout.vue";

export default {
  name: "App",
  components: {
    HeaderLayout,
    SidebarLayout,
    SidebarRight,
    FooterLayout,
  },
};
</script>
