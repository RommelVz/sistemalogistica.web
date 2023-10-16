<template>
  <div>
    <JcLoader :load="load"></JcLoader>
  <AdminTemplate :page="page" :modulo="modulo">
     <div slot="body">
       <div class="row">
           <div class="col-xl-3 col-sm-6 mb-xl-0 mb-4">
             <div class="card">
               <div class="card-body p-3">
                 <div class="row">
                   <div class="col-8">
                     <div class="numbers">
                       <p class="text-sm mb-0 text-capitalize font-weight-bold">
                         Articulos
                       </p>
                       <h5 class="font-weight-bolder mb-0">
                        {{dashboard.articulos}}
                         <span class="text-success text-sm font-weight-bolder"
                           ></span
                         >
                       </h5>
                     </div>
                   </div>
                   <div class="col-4 text-end">
                     <div
                       class="icon icon-shape bg-gradient-primary shadow text-center border-radius-md"
                     >
                       <i
                         class="ni ni-money-coins text-lg opacity-10"
                         aria-hidden="true"
                       ></i>
                     </div>
                   </div>
                 </div>
               </div>
             </div>
           </div>
           <div class="col-xl-3 col-sm-6 mb-xl-0 mb-4">
             <div class="card">
               <div class="card-body p-3">
                 <div class="row">
                   <div class="col-8">
                     <div class="numbers">
                       <p class="text-sm mb-0 text-capitalize font-weight-bold">
                        Usuarios
                       </p>
                       <h5 class="font-weight-bolder mb-0">
                        {{dashboard.usuarios}}
                         <span class="text-success text-sm font-weight-bolder"
                           ></span
                         >
                       </h5>
                     </div>
                   </div>
                   <div class="col-4 text-end">
                     <div
                       class="icon icon-shape bg-gradient-primary shadow text-center border-radius-md"
                     >
                       <i
                         class="ni ni-world text-lg opacity-10"
                         aria-hidden="true"
                       ></i>
                     </div>
                   </div>
                 </div>
               </div>
             </div>
           </div>
           <div class="col-xl-3 col-sm-6 mb-xl-0 mb-4">
             <div class="card">
               <div class="card-body p-3">
                 <div class="row">
                   <div class="col-8">
                     <div class="numbers">
                       <p class="text-sm mb-0 text-capitalize font-weight-bold">
                         Total Compras
                       </p>
                       <h5 class="font-weight-bolder mb-0">
                        {{Number(dashboard.compras).toFixed(2)}}
                         <span class="text-danger text-sm font-weight-bolder"
                           ></span
                         >
                       </h5>
                     </div>
                   </div>
                   <div class="col-4 text-end">
                     <div
                       class="icon icon-shape bg-gradient-primary shadow text-center border-radius-md"
                     >
                       <i
                         class="ni ni-paper-diploma text-lg opacity-10"
                         aria-hidden="true"
                       ></i>
                     </div>
                   </div>
                 </div>
               </div>
             </div>
           </div>
           <div class="col-xl-3 col-sm-6">
             <div class="card">
               <div class="card-body p-3">
                 <div class="row">
                   <div class="col-8">
                     <div class="numbers">
                       <p class="text-sm mb-0 text-capitalize font-weight-bold">
                         Ventas
                       </p>
                       <h5 class="font-weight-bolder mb-0">
                        {{Number(dashboard.ventas).toFixed(2)}}
                         <span class="text-success text-sm font-weight-bolder"
                           ></span
                         >
                       </h5>
                     </div>
                   </div>
                   <div class="col-4 text-end">
                     <div
                       class="icon icon-shape bg-gradient-primary shadow text-center border-radius-md"
                     >
                       <i
                         class="ni ni-cart text-lg opacity-10"
                         aria-hidden="true"
                       ></i>
                     </div>
                   </div>
                 </div>
               </div>
             </div>
           </div>
         </div>
         <div class="row mt-4">
           <div class="col-lg-7 mb-lg-0 mb-4">
           </div>
           <div class="col-lg-5">
           </div>
         </div>
         <div class="row mt-4">
           <div class="col-lg-6 mb-lg-0 mb-4">
             <div class="card z-index-2">
               <div class="card-body p-3">
                 <div class="border-radius-lg py-3 pe-1 mb-3">
                  <h6>Promedio de Inventario</h6>
                   <div class="chart">
                     <canvas
                       id="chart-bars2"
                       class="chart-canvas"
                       height="170"
                     ></canvas>
                   </div>
                 </div>
               </div>
             </div>
           </div>
            <div class="col-lg-6 mb-lg-0 mb-4">
               <div class="card z-index-2">
                 <div class="card-body p-3">
                   <div class="border-radius-lg py-3 pe-1 mb-3">
                    <h6>Ventas Mensuales</h6>
                     <div class="chart">
                       <canvas
                         id="chart-bars"
                         class="chart-canvas"
                         height="170"
                       ></canvas>
                     </div>
                   </div>
                 </div>
               </div>
             </div>
           <div class="col-lg-12">
             <div class="card z-index-2">
               <div class="card-header pb-0">
                 <h6>Ventas por meses</h6>
                 <p class="text-sm">
                   <i class="fa fa-arrow-up text-success"></i>
                   <span class="font-weight-bold">4% more</span> in 2023
                 </p>
               </div>
               <div class="card-body p-3">
                 <div class="chart">
                   <canvas
                     id="chart-line"
                     class="chart-canvas"
                     height="300"
                   ></canvas>
                 </div>
               </div>
             </div>
           </div>
           <div class="col-lg-12">
               <div class="card z-index-2">
                 <div class="card-header pb-0">
                   <h6>Ventas por Diarias</h6>
                   <p class="text-sm">
                     <i class="fa fa-arrow-up text-success"></i>
                     <span class="font-weight-bold"></span> in 2023
                   </p>
                 </div>
                 <div class="card-body p-3">
                   <div class="chart">
                     <canvas
                       id="chart-line2"
                       class="chart-canvas"
                       height="300"
                     ></canvas>
                   </div>
                 </div>
               </div>
             </div>
         </div>

     </div>
  </AdminTemplate>
</div>
 </template>

 <script>
 export default {
   name: "IndexPage",
   head() {
     return {
       title: "Index",
     };
   },
   data(){
     return {
       user:{},
       page:'Dashboard',
       modulo:'Dashboard',
       load:false,
       dashboard:{
        meses:[]
       }
     }
   },
   methods: {
    async GET_DATA(path) {
      const res = await this.$api.$get(path);
      return res;
    },
  },
   mounted(){
     this.$nextTick(()=>{
       let user = localStorage.getItem('userAuth')
       this.user = JSON.parse(user)
       this.$nextTick(async () => {
         let self = this

        this.load=true


          try{
            await Promise.all([this.GET_DATA('dashboard')]).then((v)=>{
            this.dashboard = v[0]
            console.log(this.dashboard)
          })

          }catch(e){

          }finally{

         this.load=false
         var ctx = document.getElementById("chart-bars").getContext("2d");

           new Chart(ctx, {
             type: "bar",
             data: {
               labels: this.dashboard.ventameses.map((c) => c.mes),
               datasets: [
                 {
                   label: "Ventas",
                   borderWidth: 1,
                   backgroundColor: "#3498db", // Cambiar el color de fondo de las barras a un azul claro
                   data: this.dashboard.ventameses.map((c) => c.total),
                 },
               ],
             },
             options: {
               responsive: true,
               maintainAspectRatio: false,
               plugins: {
                 legend: {
                   display: false,
                 },
               },
               interaction: {
                 intersect: false,
                 mode: "index",
               },
               scales: {
                 y: {
                   beginAtZero: true,
                   ticks: {
                     font: {
                       size: 14,
                       color: "black", // Cambiar el color de las letras a blanco puro
                     },
                     suggestedMin: 0,
                   },
                   title: {
                     display: true,
                     text: "Monto S/.",
                     color: "black", // Cambiar el color del título a blanco puro
                   },
                 },
                 x: {
                   display: true,
                   ticks: {
                     font: {
                       size: 14,
                       color: "black", // Cambiar el color de las letras a blanco puro
                     },
                   },
                   title: {
                     display: true,
                     text: "Mes",
                     color: "black", // Cambiar el color del título a blanco puro
                   },
                 },
               },
               title: {
                 display: true,
                 text: "Ventas Mensuales",
                 fontSize: 16,
                 color: "black", // Cambiar el color del título a blanco puro
               },
             },
           });

         var ctx = document.getElementById("chart-bars2").getContext("2d");

           new Chart(ctx, {
             type: "line",
             data: {
               labels: this.dashboard.promedioInventario.map((c) => c.fecha),
               datasets: [
                 {
                   label: "Promedio de Inventario",
                   borderWidth: 1,
                   backgroundColor: "#3498db", // Cambiar el color de fondo de las barras a un azul claro
                   data: this.dashboard.promedioInventario.map((c) => c.promedio_inventario),
                 },
               ],
             },
             options: {
               responsive: true,
               maintainAspectRatio: false,
               plugins: {
                 legend: {
                   display: false,
                 },
               },
               interaction: {
                 intersect: false,
                 mode: "index",
               },
               scales: {
                 y: {
                   beginAtZero: true,
                   ticks: {
                     font: {
                       size: 14,
                       color: "black", // Cambiar el color del texto a negro
                     },
                     suggestedMin: 0,
                   },
                   title: {
                     display: true,
                     text: "Monto s/.",
                     color: "black", // Cambiar el color del título a negro
                   },
                 },
                 x: {
                   display: true,
                   ticks: {
                     font: {
                       size: 14,
                       color: "black", // Cambiar el color del texto a negro
                     },
                   },
                   title: {
                     display: true,
                     text: "Mes",
                     color: "black", // Cambiar el color del título a negro
                   },
                 },
               },
               title: {
                 display: true,
                 text: "Promedio de Inventario",
                 fontSize: 16,
                 color: "black", // Cambiar el color del título a negro
               },
             },
           });







          var ctx3 = document.getElementById("chart-line").getContext("2d");

          var gradientStroke1 = ctx3.createLinearGradient(0, 230, 0, 50);

          gradientStroke1.addColorStop(1, "rgba(203,12,159,0.2)");
          gradientStroke1.addColorStop(0.2, "rgba(72,72,176,0.0)");
          gradientStroke1.addColorStop(0, "rgba(203,12,159,0)"); //purple colors

          var gradientStroke2 = ctx3.createLinearGradient(0, 230, 0, 50);

          gradientStroke2.addColorStop(1, "rgba(20,23,39,0.2)");
          gradientStroke2.addColorStop(0.2, "rgba(72,72,176,0.0)");
          gradientStroke2.addColorStop(0, "rgba(20,23,39,0)"); //purple colors

           new Chart(ctx3, {
             type: "line",
             data: {
               labels: self.dashboard.ventameses.map((m) => m.mes),
               datasets: [
                 {
                   label: "Ventas",
                   borderColor: "#4CAF50", // Color verde para ventas
                   pointBackgroundColor: "#4CAF50", // Color de los puntos
                   data: self.dashboard.ventameses.map((m) => m.total),
                 },
                 {
                   label: "Compras",
                   borderColor: "#FF5733", // Color naranja para compras
                   pointBackgroundColor: "#FF5733", // Color de los puntos
                   data: self.dashboard.comprameses.map((m) => m.total),
                 },
               ],
             },
             options: {
               responsive: true,
               maintainAspectRatio: false,
               plugins: {
                 legend: {
                   display: true, // Mostrar la leyenda
                   position: 'top', // Posición de la leyenda
                 },
                 tooltips: {
                   mode: 'index',
                   intersect: false,
                 },
               },
               scales: {
                 y: {
                   beginAtZero: true,
                   grid: {
                     display: true,
                   },
                   ticks: {
                     font: {
                       size: 12,
                     },
                   },
                   title: {
                     display: true,
                     text: "Monto S/.",
                   },
                 },
                 x: {
                   grid: {
                     display: true,
                   },
                   ticks: {
                     font: {
                       size: 12,
                     },
                   },
                   title: {
                     display: true,
                     text: "Mes",
                   },
                 },
               },
               title: {
                 display: true,
                 text: "Ventas y Compras Mensuales",
                 fontSize: 16,
               },
             },
           });


           var ctx3 = document.getElementById("chart-line2").getContext("2d");

           var gradientStroke1 = ctx3.createLinearGradient(0, 230, 0, 50);

           gradientStroke1.addColorStop(1, "rgba(203,12,159,0.2)");
           gradientStroke1.addColorStop(0.2, "rgba(72,72,176,0.0)");
           gradientStroke1.addColorStop(0, "rgba(203,12,159,0)"); //purple colors

           var gradientStroke2 = ctx3.createLinearGradient(0, 230, 0, 50);

           gradientStroke2.addColorStop(1, "rgba(20,23,39,0.2)");
           gradientStroke2.addColorStop(0.2, "rgba(72,72,176,0.0)");
           gradientStroke2.addColorStop(0, "rgba(20,23,39,0)"); //purple colors

           new Chart(ctx3, {
             type: "bar",
             data: {
               labels: self.dashboard.ventasdias.map((m) => m.fecha),
               datasets: [
                 {
                   label: "Ventas",
                   backgroundColor: "#4CAF50", // Color verde para ventas
                   data: self.dashboard.ventasdias.map((m) => m.total),
                 },
                 {
                   label: "Compras",
                   backgroundColor: "#FF5733", // Color naranja para compras
                   data: self.dashboard.comprasdias.map((m) => m.total),
                 },
               ],
             },
             options: {
               responsive: true,
               maintainAspectRatio: false,
               plugins: {
                 legend: {
                   display: true, // Mostrar la leyenda
                   position: 'top', // Posición de la leyenda
                 },
                 tooltips: {
                   mode: 'index',
                   intersect: false,
                 },
               },
               scales: {
                 y: {
                   beginAtZero: true,
                   grid: {
                     display: true,
                   },
                   ticks: {
                     font: {
                       size: 12,
                     },
                   },
                 },
                 x: {
                   grid: {
                     display: false,
                   },
                   ticks: {
                     font: {
                       size: 12,
                     },
                   },
                 },
               },
               title: {
                 display: true,
                 text: "Ventas y Compras Diarias",
                 fontSize: 16,
               },
             },
           });



          }
        });


     })
   }
 };
 </script>
