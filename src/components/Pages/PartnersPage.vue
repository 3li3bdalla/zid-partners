<template>
  <div class="container p-3">
    <div class="row">
      <div href="#" style="margin-top:90px" class=" item col-md-4 pt-5 shadow-sm  border-darken-3 border  border-blue  bg-white" v-for="partner of partners" :key="partner.id">
        <div
           class=" text-center  rounded-bottom"
        >
          <div class="partner-icon mx-auto ">
            <i class="  mx-auto p-3 rounded-circle shadow" style="width:120px;height:120px;  background-color: white;" :class="partner.icon"></i>
          </div>
          <div class="mt-3 h3 heading">
            {{  partner.name }}
          </div>
          <div style="height: 200px;overflow:hidden" class="px-3 py-1 heading pb-3">
          {{  partner.description }}
          </div>
          <div class="my-3">
            <button class="btn btn-primary">استعرض الخدمات</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      partners:[
        {
          id:1,
          name:"الشحن والتوصيل",
          description:"في القائمة أدناه - يمكنك الوصول لأعضاء المنظومة المتعهدين بخدمة توصيل طلباتك من العنوان الذي تحدده : محلك، مستودعك أو منزلك إلى عميل متجرك. بمجرد اختيارك و تفعيلك لتلك الجهات ستكون قادر على الحصول على أسعار خاصة بالشحن تم الاتفاق عليها مسبقًا مع الشركات والربط التقني المباشر وتفعيل خدماتهم. سيتم إنشاء حساب خاص بك لدى الشركة بمعلوماتك.",
          icon:"fa fa-truck"
          
        },
         {
          id:2,
          name:"الدفع",
          description:"عند تفعيلك لبوابات الدفع الموضحة ادناه، ستتمكن من ربط متجرك الإلكتروني بإحدى تلك البوابات المختلفة. كل بوابة من البوابات لديها إشتراطات معينة لتفعيل حسابك لديهم. خيارات الدفع تتيح لك استقبال المدفوعات الإلكترونية عبر البطاقات الإئتمانية وبعضهم يدعم خيار: مدى، للدفع الإلكتروني سنقوم بربطك الكترونيًا معهم ولكنك بحاجة أيضًا الى تفعيل اشتراكك لديهم وتعبئة النماذج اللازمة.",
          icon:"fa fa-credit-card"
          
        },
         {
          id:3,
          name:"تخزين المنتجات وإدارة الطلبات",
          description:"يمكنك التعاون مع مزودي خدمة التعهيد الخارجي إلى تفويض طرف ثالث بتخزين بضاعتك وتجهيز أي طلبات تصل لمتجرك الإلكتروني. ستحصل على عرض خاص عند التقديم من هنا ، إلى جانب ربط ومزامنة مخزون متجرك مع مخزونك الفعلي وتجهيز أي طلب يرد إلى متجرك بشكل مباشر.",
          icon:"fa fa-ticket"
          
        },
         {
          id:4,
          name:"التصوير",
          description:"يقدم لك مزودي خدمات التصوير خدمة تصوير المنتجات للمتاجر الإلكترونية. تلك الجهات قامت بتحديد أسعار خاصة لتجّار زد، ولديهم خبرة خاصة في تصوير المنتجات للمتاجر الإلكترونية. تقدم بطلبك الآن عبر النموذج أدناه.",
          icon:"fa fa-camera"
          
        },
         {
          id:5,
          name:"التصميم",
          description:"شركات التصميم الموجودة، بتساعدك في تصميم هويتك التجارية وتصاميمك المختلفة لاستخدامها بشكل مطبوع أو في حسابات قنوات التواصل الاجتماعي. اتفقنا معاهم على أسعار محددة وتقدر تطلع على خدماتهم وتقدم عليها من هالصفحة.",
          icon:"fa fa-paint-brush"
          
        },
        {
          id:6,
          name:"وحدات التخزين",
          description:"يمكنك التعاون مع مزودي خدمات وحدات التخزين الذاتية والحصول على أسعار خاصة لتجار زد",
          icon:"fa fa-cloud"
          
        }
      ]
    }
  },
};
</script>

<style scoped>
.heading {
      color: #a2a2a2;
}

.partner-icon {
  width: 90%;
  font-size: 80px;
  position: absolute;
  color: #9261ac;
  top: -80px;

}

.item {
  transition: all 0.7s ease-in-out;
}
.item:hover {
}

a {
  text-decoration: none !important;
}
</style>