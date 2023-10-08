<template>
  <div>
  <JcLoader :load="load"></JcLoader>
 <AdminTemplate  :page="page" :modulo="modulo">
    <div slot="body">
     <div class="row justify-content-center">

      <div class="col-sm-8 col-12">
        <div class="card">
          <div class="card-header">
            <h3>Actualizar</h3>
          </div>
          <div class="card-body">
            <CrudUpdate :valid="valid" :model="model" :apiUrl="apiUrl">
              <div slot="body" class="row">
                    <div class="form-group col-12">
              <label for="">Nombre</label>
              <input
                type="text"
                name=""
                v-model="model.nombre"
                class="form-control"
                @input="validText"
              />
            </div>
            <div class="form-group col-12">
  <label for="">Tipo de Usuario</label>
  <select
    name=""
    v-model="model.tipo"
    class="form-control"
    @input="validText"
  >
    <option value="1">Administrador</option>
    <option value="2">Usuario</option>
  </select>
</div>
                    <div class="form-group col-12">
              <label for="">Username</label>
              <input
                type="text"
                name=""
                v-model="model.username"
                class="form-control"
                @input="validText"
              />
            </div>
                    <div class="form-group col-12">
              <label for="">Email</label>
              <input
                type="email"
                name=""
                v-model="model.email"
                class="form-control"
                @input="validText"
              />
            </div>
                    <div class="form-group col-12">
              <label for="">Password</label>
              <input
                type="password"
                name=""
                v-model="model.password"
                class="form-control"
                @input="validText"
              />
            </div>

                  </div>
                </CrudUpdate>
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
            title: "Usuario",
        };
        ;
    },
    data() {
        return {
          load:true,

         model: {
        nombre: "",
        username:'',
        email:'',
        password:'',
        tipo:''
      },
          apiUrl:'users',
          page:'Usuarios',
      modulo:'Usuario',
      valid:false
        };
    },
    methods: {
      async GET_DATA(path) {
            const res = await this.$api.$get(path);
            return res
        },
        validText(){
    const emailRegex = /^[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,4}$/;
    console.log(!emailRegex.test(this.model.email));
    let noEsValido = (this.model.nombre === "" || this.model.tipo === "" || this.model.password === "" || this.model.username === "" || this.model.email === ""||!emailRegex.test(this.model.email));
    this.valid = noEsValido;
  },

    },
    mounted() {
        this.$nextTick(async () => {

          try{
            await Promise.all([this.GET_DATA(this.apiUrl+'/'+this.$route.params.id)]).then((v)=>{
              this.model = v[0]
            })
          }catch(e){
            console.log(e);
          }finally{
            this.load = false
          }



        });
    }
};
</script>
