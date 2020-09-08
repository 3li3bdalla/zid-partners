<template>
  
  <div id="status-bar" class="container-fluid">
            <div class="row">
                <div class="col-3 col-md-5 col-lg-5">
                    <div class="time-holder">
                        <button class="btn-menu-toggle" @click="toggleSideBarStatus">
                            <div class="toggle-icon">
                                <div class="icon-shape"></div>
                            </div>
                        </button>
                        <div class="time"><i class="zid zid-clock"></i>الساعة {{ currentDate }} {{ currentDateType }} بتوقيت الرياض</div>
                    </div>
                </div>
                <div class="col-9 col-md-7 col-lg-7">
                    <div class="search-holder">
                        <form><input type="text" placeholder="إبحث هنا..."><button type="submit"><i class="zid zid-find"></i></button></form>
                        <a class="btn-logout" href="#"><span class="text">تسجيل خروج</span><i class="zid zid-exit"></i></a>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {
    data:function() {
        return {
            currentDate:(new Date).getSeconds() + ":" +(new Date).getMinutes() + ":" + ((new Date).getHours() % 12),
            currentDateType:(new Date).getHours() >= 12 ? "مساءاً" : "صباحاً"
        }
    },
    created() {
        let appVm = this;
        setInterval(() => {
            appVm.currentDate = (new Date).getSeconds() + ":" +(new Date).getMinutes() + ":" + ((new Date).getHours() % 12)
            appVm.currentDateType = (new Date).getHours() >= 12 ? "مساءاً" : "صباحاً"
 
        },1000)
    },
     methods:{
         toggleSideBarStatus()
        {
            

            let newStatus = localStorage.getItem('zid-sidebar-status') == null ? false : !localStorage.getItem('zid-sidebar-status');
                        // console.log(sideBarStatus);
            localStorage.setItem('zid-sidebar-status',newStatus);
            this.$emit('sideBarStatusToggled',{status:newStatus})
        }
     }
}
</script>

<style>

</style>>