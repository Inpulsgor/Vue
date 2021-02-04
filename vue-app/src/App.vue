<template>
    <Container>
      <AppartementsList :items="appartements">
        
      </AppartementsList>
    </Container>
</template>

<script>
import Container from './components/shared/Container';
import AppartementsList from './components/AppartementsList';
import appartements from './services/data';

export default {
  name: 'App',
  components: {
    Container,
    AppartementsList
  },
  data() {
    return {
      appartements
    }
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
