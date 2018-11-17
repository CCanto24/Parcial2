<template>
<div>
    <center>
       <h1 align="center"> Ingrese los datos de Usuario </h1>>
     <el-col :span="12">
      <div class="grid-content">
        <el-input placeholder="Nombre" v-model="Nombre" ></el-input>
        <br>
        <br>
        <el-input placeholder="Apellido" v-model="Apellido" ></el-input>
        <br>
        <br>
        <div> 
            <el-select placeholder="Provincia" v-model="Ciudad">
                <el-option
                v-for="item in provincias"
                :key="item.provincia"
                :label="item.label"
                :value="item.value">
                </el-option>
            </el-select>
        </div>
        <br>
        <p> Sexo: </p>
        <el-radio v-model="Sexo" label="1">Masculino</el-radio>
        <el-radio v-model="Sexo" label="2">Femenino</el-radio>
        <br>
        <p> Estado Civil: </p>
        <el-radio v-model="EstCiv" Label="1">Soltero/a</el-radio>
        <el-radio v-model="EstCiv" Label="2">Casado/a</el-radio>
        <el-radio v-model="EstCiv" Label="3">Divorciado/a</el-radio>
        <el-radio v-model="EstCiv" Label="4">Viudo/a</el-radio>
        <br>
        <p> Estado: </p>
        <el-radio v-model="Estado" Label="1">Activo</el-radio>
        <el-radio v-model="Estado" Label="2">Inactivo</el-radio>
        <br>
        <br>
        <el-input placeholder="Dirección" v-model="Direccion"></el-input>
        <br>
        <br>
      </div>
      </el-col>
      </center>
</div>

</template>
<script>
export default {
    name:"formulario",
    data: function() {

    }

}
</script>
