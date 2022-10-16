<template>
  <h1>Template Syntax</h1>

  <h4>1. Text Interpolation</h4>
  <p>{{title}}</p>
  <p>{{isItTrue}}</p>
  <p>{{cars[0]}}</p>
  <p>{{myobj.name}} : {{myobj.age}}</p>
  <p v-text="title1"></p>

  <h4>2. Functions</h4>
  <p>{{greeting()}}</p>
  <p>{{greetings()}}</p>
  <p>{{usingthis()}}</p>
  <p>{{arrow()}}</p>

  <h4>3. Bindings</h4>
  <img src="../assets/logo.png" alt="alt tag" /><br>
  <a v-bind:href="link">link</a><br>
  <a :href="link">link shorthand</a><br>

  <h4>4. Attribute Bindings</h4>
  <p v-bind:id="headingID">Heading Title</p><!-- <p id="heading">Heading Title</p> -->
  <button v-bind:disabled="isDisabled">Submit</button><!-- <button disabled>Submit</button> -->

  <h4>5. Binding Classes</h4>
  <p class="underline">Static Class</p>
  <p class="underline" v-bind:class="status">Dynamic Class</p>
  <p v-bind:class="isPromoted && 'promoted'">Promoted Movie</p>
  <p v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout? Movie</p>
  <p v-bind:class="['new', 'promoted']">Arry with css style class</p>
  <p v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Arry conditional</p>
  <p v-bind:class="{promoted: isPromoted, new: !isSoldout, 'sold-out': isSoldout}">Object conditional </p>

  <h4>6. Binding Styles</h4>
  <p v-bind:style="{color: highlightColor,'font-size': paragraphSize + 'px', /* 'fonSize': paragraphSize + 'px' */ padding: '20px'}">Inline Style</p>
  <p v-bind:style="paraStyleObject">Style Object</p>
  <div v-bind:style="[baseStyleObject, successObjectClass]">Style Array</div>

  <h4>7. Raw HTML</h4>
  <p v-html="myHtml"></p>

  <h4>8. Directive: v-if, v-else-if, v-else</h4>
  <p v-if="userAge >= allowedAge">You are good to go</p>
  <p v-else-if="user==='Moana'">You are good</p>
  <!-- <p>can't use any html element within the if, else directives, then it will not work</p> -->
  <p v-else>You are not good to go</p>

  <h4>9. Directive: v-show</h4>
  <p v-show="login==='user'">Logged In</p>
  <p v-show="login!=='user'">Guest</p>

  <h4>10. Directive: v-once</h4>
  <p>{{fruit}}</p>
  <p v-once>{{fruit}}</p><!-- only the 1st variable will change -->
  <p>{{update()}}</p>

  <h4>11. Directive: v-on</h4>
  <p>{{myname}}</p>
  <button v-on:click="updateName">click</button>

  <h4>12. Argument & Modifier</h4>
  <p>{{company}}</p>
  <button v-on:click.left="updateCompany('FNF Desk', $event)">click</button>

  <h4>13. Argument & Modifier</h4>
  <form v-on:submit="handleForm">
    <input type="text">
    <button type="submit">submit</button>
  </form>

  <h4>14. Argument & Modifier</h4>
  <form v-on:submit.prevent="handleForm2">
    <input type="text">
    <button type="submit">submit</button>
  </form>

  <h4>15. v-model</h4>
  <form v-on:submit.prevent="handleForm3">
    <label>First Name:</label>
    <input type="text" v-model="formData.firstName"><br><br>

    <label>Last Name:</label>
    <input type="text" v-model="formData.lastName"><br><br>

    <button type="submit">submit</button>
  </form>

  <h4>16. Using JavaScript Expressions</h4>
  <p>Current Date & Time: {{currentDateTime()}}</p>

</template>

<script>
export default {
  name: 'TemplateSyntax',
  data() {
    return {
      /* 1. Text Interpolation */
      title: 'Moana',
      isItTrue: true,
      cars: ['Ford', 'Toyota'],
      myobj: {
        name: 'Mamma',
        age: 3
      },
      title1: 'Mamun',
      /* 3. Bindings */
      alt: 'Vue JS',
      link: 'https://vuejs.org/',
      /* 4. Attribute Bindings */
      headingID: 'heading',
      isDisabled: true,
      /* 5. Binding Classes */
      status: 'danger',
      isPromoted: true,
      isSoldout: true,
      /* 6. Binding Styles */
      highlightColor: 'orange',
      paragraphSize: 50,
      paraStyleObject: {
        color: 'red',
        fontSize: '30px',
        padding: '20px'
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px'
      },
      successObjectClass: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid red',
      },
      /* 7. Raw HTML */
      myHtml: '<b>My html</b>',
      /* 8. Directive: v-if, v-else-if, v-else */
      user: 'Moana',
      userAge: 10,
      allowedAge: 7,
      /* 9. Directive: v-show */
      login:'user',
      /* 10. Directive: v-once */
      fruit: 'Mango',
      /* 11. Directive: v-on */
      myname: 'Mamun',
      /* 12. Argument & Modifier */
      company: 'FNF',
      /* 15. v-model */
      formData: {
        firstName: '',
        lastName: ''
      },
    }
  },
  methods: {
    /* 2. Functions */
    greeting: function () {
      return 'Usual function';
    },
    greetings() {
      return 'ES6 Function';
    },
    usingthis() {
      return this.title;
    },
    arrow: () => {
      return 'Arrow Function';
    },
    /* 10. Directive: v-once */
    update() {
      setTimeout(() => {
        return this.fruit = 'Apple';
      }, 2000)
    },
    /* 11. Directive: v-on */
    updateName() {
      return this.myname = 'Moana';
    },
    /* 12. Argument & Modifier */
    updateCompany(newcom, event) {
      console.log(event);
      return this.company = newcom;
    },
    /* 13. Argument & Modifier */
    handleForm(event) {
      event.preventDefault();
      console.log('submit form');
    },
    /* 14. Argument & Modifier */
    handleForm2() {
      console.log('submit form');
    },
    /* 15. v-model */
    handleForm3() {
      console.log(this.formData.firstName);
      console.log(this.formData.lastName);
    },
    currentDateTime() {
      const current = new Date();
      const date = current.getFullYear() + '-' + (current.getMonth() + 1) + '-' + current.getDate();
      const time = current.getHours() + ":" + current.getMinutes() + ":" + current.getSeconds();
      const dateTime = date + ' ' + time;

      return dateTime;
    }

  }
}


</script>

<style>
.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: green;
}

.sold-out {
  color: red;
}

.danger {
  color: red;
}
</style>