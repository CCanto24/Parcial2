 <template>
    <div>
        <center v-if="!check">
            <h2> Inicio de Sesión </h2>
            <p>Ingrese su usuario y contraseña </p>
            <el-input size="medium" placeholder="Usuario" v-model="User"></el-input>
            <br>
            <br>
            <el-input size="medium" placeholder="Contraseña" v-model="Pass" type="password"></el-input>
            <br>
            <br>
            <el-button type="primary" @click="validar" >Ingresar </el-button>

        </center>
        <center v-if="check">
            <formulario/> 

        </center>

    </div>
</template>
<script>
import formulario from './Formulario.vue'

export default {
    name: "login",
    components:{
        formulario
    },
    data: function(){
        return {
            User:'',
            Pass:'',
            check: false,
        }
    },
       methods:
       {
            validar: function()
            {
            if (this.User === 'admin' && this.Pass === 'admin')
                {
                 this.check = true
                }
            else 
                {
                alert('Usuario o Contraseña no valido')
                document.getElementById("nombre").value="";
                document.getElementById("clave").value="";
                document.getElementById("nombre").focus();
                }
            }
       }
}
</script>
