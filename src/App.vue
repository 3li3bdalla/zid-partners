<template>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
    <title>Zid - Panel</title>
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/bootstrap.min.css">
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/bootstrap-rtl.min.css">
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/bootstrap-custom-colors.css">
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" integrity="sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN" crossorigin="anonymous">    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/slick.css">
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/bootstrap-datepicker.css">
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/chosen.min.css">
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/style.css">
    <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/style-rtl.css">
    <!-- <link rel="stylesheet" type="text/css" href="http://brandio.io/works/zid19/css/dark-mode.css" v-if='isDarkModeStatus'> -->
</head>
<body>
  <div id="app">
    <div id="wrapper">
      <div id="sidebar-wrapper" :class="[sideBarStatus ? 'open' : 'close']" >
          <button class="btn-menu-close"  ><i class="zid zid-close"></i></button>
          <SideBarLayout @isDarkModeStatusToggled="isDarkModeStatusToggled"></SideBarLayout>
      </div>
    </div>
    <div id="page-content-wrapper" :class="{ 'full-screen-size' :!sideBarStatus }">
      <StatusBarLayout @sideBarStatusToggled="sideBarStatusToggled"></StatusBarLayout>
       <div class="container-fluid page-head">
            <div class="row">
                <div class="col-md-12">
                    <div class="page-title"  >طرق الدفع</div>
                    <ol class="breadcrumb breadcrumb-sm">
                        <li class="breadcrumb-item"><a href="settings.html">الإعدادات</a></li>
                        <li class="breadcrumb-item active">طرق الدفع</li>
                    </ol>
                </div>
            </div>
        </div>

        <PartnersPage></PartnersPage>

        <!-- <PaymentMethodsPage></PaymentMethodsPage> -->
        <FooterLayout></FooterLayout>

    </div>

  </div>
</body>
</html>
</template>

<script>
// import PanelPage from './components/Pages/PanelPage'
import SideBarLayout from './components/Layouts/SideBarLayout'
import StatusBarLayout from './components/Layouts/StatusBarLayout'
import FooterLayout from './components/Layouts/FooterLayout'
import PartnersPage from './components/Pages/PartnersPage'
// import PaymentMethodsPage from './components/Pages/PaymentMethodsPage'

export default {
  name: 'App',
  components: {
    StatusBarLayout,
    SideBarLayout,
    FooterLayout,
    PartnersPage,
    // PaymentMethodsPage
  },
  data() {
    return {
      isDarkModeStatus:localStorage.getItem('zid-panel-darkmode') == null ? false : localStorage.getItem('zid-panel-darkmode'),
      sideBarStatus:localStorage.getItem('zid-sidebar-status') == null ? false : localStorage.getItem('zid-sidebar-status')
    }
  },
  methods: {
   sideBarStatusToggled(e)
   {
     this.sideBarStatus = e.status
   },
   isDarkModeStatusToggled(e)
   {
     this.isDarkModeStatus = e.status
   }
  }
}
</script>

<style>
.full-screen-size {
  margin-right:0px !important
}
</style>
