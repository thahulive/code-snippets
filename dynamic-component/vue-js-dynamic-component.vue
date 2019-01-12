<template>
  <div>
    <component 
      :is="template" />
  </div>
</template>

<script>

export default {
    data() {
        return {
            isAdminUser: true
        }
    },
    computed: {
        template() {
            let template = (this.isAdminUser) ? 'admin-dashboard' : 'user-dashboard'
            return () => import(`example-components/${template}.vue`)
        }
    }
}
</script>
