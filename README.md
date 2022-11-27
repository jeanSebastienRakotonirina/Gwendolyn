# Vue JS

## Events & Methods

1. v-on is used for events like click event

html :

    <button v-on:click="isVisible = !isVisible">Toggle Box</button>

When I click once on the button, if isVisible is false, it becomes true. And when I click against, it turns to false.  

"v-on:click" can be written like this "@click"

html :

    <button v-on:click="toggleBox">Toggle Box</button>

The methods is called toggleBox here. I now, I need to create it.

script :

        let app = Vue.createApp({
            data: function(){
                return {
                    greeting: 'Hello Vue 3!',
                    isVisible: false,
                }
            },
            methods: {
                toggleBox: function(){
                    this.isVisible = !this.isVisible
                }
            }
        })

To do that, we create a function named toggleBox in methods.

2. v-on:keyup is a keyboard event

html :

        <input @keyup.enter="greet" type="text" name="test" id="test" v-model="greeting">

script :

            methods: {
                toggleBox: function(){
                    this.isVisible = !this.isVisible
                },
                greet(){
                    console.log(this.greeting)
                }
            }

When I push Enter on the keyboard, it will launch the greet method. 

html :

        <input @keyup.enter="greet(greeting + 'ffd!!!')" type="text" name="test" id="test" v-model="greeting">

Now, I passed a parameter in greet function so do I in methods.

Script :

                greet(greeting){
                    console.log(greeting)
                }

I can see what I typed in the console, not only the variable greeting we have in data, like before.

@keyup.enter is an event modifier in VueJs. There are many of then. For example, @click.right will only listening to the right mouse button click event. 

@click.prevent
@click.prevent.stop