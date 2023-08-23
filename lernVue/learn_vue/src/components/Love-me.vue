<template>
    <div>
       <h1>For loop in vue JS</h1> 
         <!-- <ul>
              <li v-for="user in users" :key="user.id">
                <h3>{{user.name}}</h3>
                <p>{{user.email}}</p>
              </li>
            </ul> -->

        <table>
            <thead>
                <tr>
                    <th>Id</th>
                    <th>Name</th>
                    <th>Email</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in users" :key="user.id">
                    <td>{{user.id}}</td>
                    <td>{{user.name}}</td>
                    <td>{{user.email}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'Love-me',
    props:{
        msg: String,
        data: String,
    },
    data(){
        return{
            users:[
                {id:1, name:"Aman", email:"aman@mail.com"},
                {id:2, name:"Rahul", email:"rahul@mail.com"},
                {id:3, name:"Sonu", email:"sonu@mail.com"},
                {id:4, name:"Kunal", email:"kunal@mail.com"},
            ]
        }
    },
}
</script>
  