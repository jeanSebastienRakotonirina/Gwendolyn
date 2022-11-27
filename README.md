# Vue JS

## Components

our application use basically one standard component app. We are going to work about breaking a part of this to several components.

html :

        <login-form></login-form>

We create a custom tag with the name of the component in html.

script :

        app.component('custom-form', {
            template: `
                <div>
                    <input type="email" />
                    <input typr="password" />
                </div>
            `
        })

It is a function which has the name of the component as first parameter and an object as the second.

script :

        app.component('login-form', {
            template: `
                <form>
                    <h1>{{ title }}</h1>
                    <input type="email" />
                    <input type="password" />
                </form>
            `,
            data(){
                return {
                    title: 'Login Form'
                }
            }
        })

It's possible to send data to the template as you see. Title is created in data and be displayed by using the variable in th template component.

template : 

    <form @submit="handleSubmit">

This creates an event on submitting the form.

methods :

            methods: {
                handleSubmit(){
                    console.log("submitted")
                }
            }

And we need to create the method 