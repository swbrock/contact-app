<template>
    <div>
         <div class="flex flex-col h-screen text-sm text-gray-400">
            <div class=" flex-1 flex">
                <!-- form -->
                <div class="sidebar w-1/3 flex-none flex flex-col justify-between">
                    <form @submit.prevent="addContact" class="mx-10 my-10 px-20">
                        <div class="">
                          <h1>Contact List</h1>
                            <h3>Add A Contact</h3>
                            <input v-model="name" type="text" placeholder="Name">
                            <input v-model="number" type="text" placeholder="Phone Number">
                            <input v-model="address" type="text" placeholder="Address">
                            <input v-model="city" type="text" placeholder="City">
                            <input v-model="state" type="text" placeholder="State">
                            <input v-model="email" type="email" placeholder="Email">
                            <input v-model="category" type="text" placeholder="Category">
                        </div>
                        <div class="">
                            <button class="bg-gray-800 py-2 px-2 text-white hover:bg-blue-500 rounded" type="submit"> Add Contact </button>                        </div>
                    </form>
                </div>
                  
                  
              <div class="items-center mt-4 ">
                <p>Name  ---  Phone Number  ---  Address  --- City  ---  State  ---  Email  ---  Category </p>
                <div v-for="(contact,index) in contacts" :key="index">
                    <p2>{{contact.name}}  ---  {{contact.number}}  ---  {{contact.address}}  ---  {{contact.city}}  ---  {{contact.state}}  ---  {{contact.email}}  ---  {{contact.category}}  ||| </p2>
                    <button type="button" @click="deleteContact(index)"> Delete </button>
                    <button type="button" @click="editContact(index)"> Edit </button>

                </div>                  
        </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            name:'',
            number:'',
            address:'',
            city:'',
            state:'',
            email:'',
            category:'',
            contacts:[]
        }
    },
    methods:{
        addContact(){
            const contact={
                name:this.name,
                number:this.number,
                address:this.address,
                city:this.city,
                state:this.state,
                email:this.email,
                category:this.category
            };
            this.contacts.push(contact)
        },
        deleteContact(index){
            this.$delete(this.contacts,index);
        },
        editContact(index){
          const contact={
            name:this.name,
            number:this.number,
            address:this.address,
            city:this.city,
            state:this.state,
            email:this.email,
            category:this.category
          };
          contact(this.contacts, index)
        }
    },
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
p {
  font-style: underline;
  font-style: bolder;
  font-family: Georgia, Times, 'Times New Roman', serif;
  position: relative;
  right: 5px;
  left: 0;
  top: padding 10%;
}
p2 {
  font-style: normal;
  font-family: Georgia, Times, 'Times New Roman', serif;
  position: relative;
  right: 5px;
  left: 0;
  top: padding 15%;
  background-color: #D7FFC2;
}
a {
  border-style:solid;
   ;
}
</style>


