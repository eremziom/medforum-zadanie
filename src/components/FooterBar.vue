<template>
  <footer 
    class="footer mt-auto py-3 footer-container"
  >
    <div 
      class="d-flex justify-content-between px-2 align-items-center"
    >
      <p 
        class="mb-0"
      >
        {{ $t('footer.for') }}
        <span 
          style="color: orange"
        >
          med
        </span>
        <span>
          forum
        </span>
      </p>
      <p 
        class="mb-0"
      >
        {{ $t('footer.right') }}
      </p>
      <p 
        class="mb-0"
      >
        @eremziom
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterBar'
}
</script>