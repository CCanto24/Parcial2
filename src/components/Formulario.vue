<template>
<div>
       <h1 align="center"> Ingrese los datos de Usuario </h1>
     <el-col :span="12">
      <div class="grid-content">
        <el-input placeholder="Nombre" v-model="NameUser" ></el-input>
        <br>
        <br>
        <el-input placeholder="Apellido" v-model="LastUser" ></el-input>
        <br>
        <br>
        <div> 
            <el-select placeholder="Provincia" v-model="ProvUser">
                <el-option
                v-for="item in provincias"
                :key="item.provincia"
                :label="item.label"
                :value="item.value">
                </el-option>
            </el-select>
        </div>
        <br>
        <br>
        <p> Sexo: </p>
        <el-radio-group v-model="SexoUser">
        <el-radio label="Masculino">Masculino</el-radio>
        <el-radio label="Femenino">Femenino</el-radio>
        </el-radio-group>
        <br>
        <br>
        <el-select placeholder="Estado Civil" v-model="EsCiUser">
                <el-option
                v-for="item in civiles"
                :key="item.civil"
                :label="item.label"
                :value="item.value">
                </el-option>
            </el-select>
        <br>
        <br>
        <p> Estado: </p>
        <el-radio v-model="EstaUser" label="Activo">Activo</el-radio>
        <el-radio v-model="EstaUser" label="Inactivo">Inactivo</el-radio>
        <br>
        <br>
        <el-input placeholder="Dirección" v-model="AddrUser"></el-input>
        <br>
        <br>
        <el-button type="primary" @click="saveUser" v-if="validUser" >Guardar </el-button>
      </div>
    
     </el-col>

     <el-col :span="12">
     <div id="ocultar1" >
        <el-table
        :data="tableData1"
        style="width: 100%">
        <el-table-column
          prop="nombre"
          label="Nombre"
          width="180">
        </el-table-column>
        <el-table-column
          prop="apellido"
          label="Apellido"
          width="180">
        </el-table-column>
        <el-table-column
          prop="provincia"
          label="Provincia"
          width="180">
        </el-table-column>
        <el-table-column
          prop="sexo"
          label="Sexo"
          width="180">
        </el-table-column>
        <el-table-column
          prop="estadoCivil"
          label="Estado Civil"
          width="180">
        </el-table-column>
        <el-table-column
          prop="estado"
          label="Estado"
          width="180">
        </el-table-column>
        <el-table-column
        prop="direccion"
        label="Dirección"
        width="180">
      </el-table-column>
      </el-table>
     </div>
     </el-col>
</div>
</template>

<script>
export default {
    name:"formulario",
    data: function() {
      return {
        NameUser:'',
        LastUser:'',
        ProvUser:'',
        AddrUser:'',
        SexoUser:'Masculino',
        EsCiUser:'',
        EstaUser:'Activo',
        provincias: [
            {value: 'Bocas del Toro', label:'Bocas del Toro'},
            {value:'Chiriquí', label:'Chiriquí'},
            {value:'Coclé', label:'Coclé'},
            {value:'Colón', label:'Colón'},
            {value:'Darién', label:'Darién'},
            {value:'Herrera', label:'Herrera'},
            {value:'Los Santos', label:'Los Santos'},
            {value:'Panamá', label:'Panamá'}
            ],
        civiles:[
            {value:'Soltero/a', label:'Soltero/a'},
            {value:'Casado/a', label:'Casado/a'},
            {value:'Divorciado/a', label:'Divorciado/a'},
            {value:'Viudo/a', label:'Viudo/a'}
        ],    
        tableData1: [{
            nombre:'',
            apellido:'',
            provincia:'',
            sexo:'',
            estadoCivil:'',
            estado: '',
            direccion:''
        }]     
      }
    },
    methods:{
        saveUser: function () {
            this.tableData1.push({
                nombre: this.NameUser,
                apellido: this.LastUser,
                provincia: this.ProvUser,
                sexo: this.SexoUser,
                estadoCivil: this.EsCiUser,
                estado: this.EstaUser,
                direccion: this.AddrUser
              });
              this.nombre= '';
              this.apellido= '';
              this.provincia= '';
              this.sexo= '';
              this.estadoCivil= '';
              this.estado= '';
              this.direccion= '';
        },
    },
    computed :{
        validUser: function (){
            return this.NameUser && this.LastUser && this.ProvUser && this.SexoUser && this.EsCiUser && this.EstaUser && this.AddrUser
                                }
              }  
}
</script>
