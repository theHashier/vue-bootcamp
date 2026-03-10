## Event Syntax

Vue allows two ways to listen to events.

Full directive syntax:

<button v-on:click="increase">Increase</button>

Shorthand syntax (commonly used):

<button @click="increase">Increase</button>

Both examples do exactly the same thing.  
`@` is simply a shorthand for the `v-on` directive.

Example:

v-on:click  →  @click
v-on:input  →  @input
v-on:submit →  @submit