<template>
  <div>
    <AppartementItem 
    :id="appartement.id"
    :title="appartement.title"
    :description="appartement.description"
    :price="appartement.price"
    :rating="appartement.rating"
    :location="appartement.location"
    imageSrc="https://cdn.pixabay.com/photo/2014/11/21/17/17/country-house-540796_960_720.jpg"
     />
  </div>
</template>

<script>
import AppartementItem from './components/AppartementItem'

export default {
  name: 'App',
  components: {
    AppartementItem
  },
  data() {
    return {
      appartement: {
        id: '5qwd35436qasd2wad13asdss',
        title: 'Brand new house in Kyiv',
        description: 'The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested.',
        price: 2021,
        rating: 4.5,
        location: {
          city: 'Kyiv'
        },
        owner: {
          name: 'Ivan',
          phone: '097-111-22-33',
          email: 'ivan@gmail.com',
        },
      }
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
