<template>
  <div class="container">
    <h1>Sistema Interno de Gestión</h1>
    <h2>Registro de Documentos</h2>

    <form @submit.prevent="guardarDocumento">
      <div class="campo">
        <label>Folio</label>
        <input type="text" v-model="documento.folio" required />
      </div>

      <div class="campo">
        <label>Fecha</label>
        <input type="date" v-model="documento.fecha" required />
      </div>

      <div class="campo">
        <label>Tipo de documento</label>
        <input type="text" v-model="documento.tipo" required />
      </div>

      <div class="campo">
        <label>Área destino</label>
        <input type="text" v-model="documento.area" required />
      </div>

      <div class="campo">
        <label>Observaciones</label>
        <textarea v-model="documento.observaciones"></textarea>
      </div>

      <h3>Datos del Solicitante</h3>

      <div class="campo">
        <label>Nombre del solicitante</label>
        <input type="text" v-model="documento.solicitante.nombre" required />
      </div>

      <div class="campo">
        <label>Tipo de solicitante</label>
        <select v-model="documento.solicitante.tipo" required>
          <option disabled value="">Seleccione una opción</option>
          <option>Ciudadano</option>
          <option>Empresa</option>
          <option>Dependencia</option>
        </select>
      </div>

      <div class="campo">
        <label>Contacto</label>
        <input type="text" v-model="documento.solicitante.contacto" />
      </div>

      <button type="submit">Guardar documento</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      documento: {
        folio: '',
        fecha: '',
        tipo: '',
        area: '',
        observaciones: '',
        solicitante: {
          nombre: '',
          tipo: '',
          contacto: ''
        }
      }
    }
  },
  methods: {
    guardarDocumento() {
      console.log('Documento registrado:', this.documento)
      alert('Documento registrado correctamente')
      this.limpiarFormulario()
    },
    limpiarFormulario() {
      this.documento = {
        folio: '',
        fecha: '',
        tipo: '',
        area: '',
        observaciones: '',
        solicitante: {
          nombre: '',
          tipo: '',
          contacto: ''
        }
      }
    }
  }
}
</script>

<style>
.container {
  max-width: 600px;
  margin: 40px auto;
  font-family: Arial, sans-serif;
}

.campo {
  margin-bottom: 15px;
}

label {
  display: block;
  font-weight: bold;
}

input,
textarea {
  width: 100%;
  padding: 6px;
}

button {
  padding: 8px 16px;
}
</style>