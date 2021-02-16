<h2 id="In_this_article">Contents</h2>

<ul>
 <li><a href="#general_javascript_guidelines">General JavaScript guidelines</a>

  <ul>
   <li><a href="#use_expanded_syntax">Use expanded syntax</a></li>
   <li><a href="#javascript_comments">JavaScript comments</a></li>
   <li><a href="#use_es6_features">Use ES6 features (unless IE11 support is required)</a></li>
  </ul>
 </li>
 <li><a href="#variables">Variables</a>
  <ul>
   <li><a href="#variable_naming">Variable naming</a></li>
   <li><a href="#declaring_variables">Declaring variables</a></li>
  </ul>
 </li>
 <li><a href="#operators_and_comparison">Operators and comparison</a>
  <ul>
   <li><a href="#ternary_operators">Ternary operators</a></li>
   <li><a href="#use_strict_equality">Use strict equality</a></li>
   <li><a href="#use_shortcuts_for_boolean_tests">Use shortcuts for boolean tests</a></li>
  </ul>
 </li>
 <li><a href="#control_statements">Control statements</a></li>
 <li><a href="#strings">Strings</a>
  <ul>
   <li><a href="#use_template_literals">Use template literals (unless IE11 support is required)</a></li>
  </ul>
 </li>
 <li><a href="#conditionals">Conditionals</a>
  <ul>
   <li><a href="#switch_statements">Switch statements</a></li>
  </ul>
 </li>
 <li><a href="#functions_and_objects">Functions and objects</a>
  <ul>
   <li><a href="#function_naming">Function naming</a></li>
   <li><a href="#defining_functions">Defining functions</a></li>
   <li><a href="#creating_objects">Creating objects</a></li>
   <li><a href="#object_classes">Object classes</a></li>
   <li><a href="#object_naming">Object naming</a></li>
  </ul>
 </li>
 <li><a href="#arrays">Arrays</a>
  <ul>
   <li><a href="#creating_arrays">Creating arrays</a></li>
  </ul>
 </li>
 <li><a href="#error_handling">Error handling</a></li>
</ul>

<h2 id="General_JavaScript_guidelines">General JavaScript guidelines</h2>

<h3 id="Use_expanded_syntax">Use expanded syntax</h3>

<p>For JavaScript we use expanded syntax, with each line of JS on a new line, the opening brace of a block on the same line as its associated statement, and the closing brace on a new line. This maximizes readability, and again, promotes consistency on MDN.</p>

<p>Do this</p>

<pre class="brush: js example-good notranslate">function myFunc() {
  console.log('Hello!');
};</pre>

<p>Not this</p>

<pre class="brush: js example-bad notranslate">function myFunc() { console.log('Hello!'); };</pre>

<p>We also have a few specific rules around spacing inside language features. You should include spaces between operators and operands, parameters, etc.</p>

<p>This is more readable</p>

<pre class="brush: js example-good notranslate">if(dayOfWeek === 7 &amp;&amp; weather === 'sunny') {
  goOnTrip('beach', 'car', ['ice cream', 'bucket and spade', 'beach towel']);
}</pre>

<p>than this</p>

<pre class="brush: js example-bad notranslate">if(dayOfWeek===7&amp;&amp;weather==='sunny'){
  goOnTrip('beach','car',['ice cream','bucket and spade','beach towel']);
}</pre>

<p>In addition, keep these specifics in mind:</p>

<ul>
 <li>Don't include padding spaces after opening brackets or before closing brackets — <code>(myVar)</code>, not <code>( myVar )</code>.</li>
 <li>All statements must end with semicolons (";"). We require them in all of our code samples even though they're technically optional in JavaScript because we feel that it leads to code that is clearer and more precise about where each statement ends.</li>
 <li>Use single quotes in JavaScript, wherever single quotes are needed in syntax.</li>
 <li>There should be a space between a control statement keyword or loop keyword and its opening parenthesis (e.g. <code>if () { ... }</code>, <code>for (...) { ... }</code>).</li>
 <li>There should be a space between the parentheses and the opening curly brace in such cases as described in the previous bullet.</li>
</ul>

<h3 id="JavaScript_comments">JavaScript comments</h3>

<p>Use JS-style comments to comment code that isn't self-documenting:</p>

<pre class="brush: js example-good notranslate">// This is a JavaScript-style comment</pre>

<p>Put your comments on separate lines preceding the code they are referring to:</p>

<pre class="brush: js example-good notranslate">function myFunc() {
  // Output the string 'Hello' to the browser's JS console
  console.log('Hello');
  // Create a new paragraph, fill it with content, and append it to the &lt;body&gt;
  let para = document.createElement('p');
  para.textContent = 'My new paragraph';
  document.body.appendChild(para);
}</pre>

<p>Also note that you should leave a space between the slashes and the comment, in each case.</p>

<h3 id="Use_ES6_features">Use ES6 features (unless IE11 support is required)</h3>

<p>Unless IE11 support is required, you can use common ES6 features (such as <a href="/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions">arrow functions</a>, <a href="/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise">promises</a>, <code><a href="/en-US/docs/Web/JavaScript/Reference/Statements/let">let</a></code>/<code><a href="/en-US/docs/Web/JavaScript/Reference/Statements/const">const</a></code>, <a href="/en-US/docs/Web/JavaScript/Reference/Template_literals">template literals</a>, and <a href="/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax">spread syntax</a>) in MDN examples. We include them in many places in these guidelines, as we believe the web industry has generally gotten to the point where such features are familiar enough to be understandable. And for those that don't use them yet, we'd like to play our part in helping people to evolve their skills.</p>

<p>However, we don't yet recommend the general use of newer ES features such as <a href="/en-US/docs/Web/JavaScript/Reference/Statements/async_function">async</a>/<a href="/en-US/docs/Web/JavaScript/Reference/Operators/await">await</a>, trailing commas on argument lists, etc. We’d prefer you not to use those unless strictly necessary, and if you do use them, include explanation in your example to say what they are doing, with a link to appropriate reference material.</p>



<h2 id="Variables">Variables</h2>

<h3 id="Variable_naming">Variable naming</h3>

<p>For variable names use lowerCamelCasing, and use concise, human-readable, semantic names where appropriate.</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">let playerScore = 0;

let speed = distance / time;</pre>

<p>Not this:</p>

<pre class="brush: js example-bad notranslate">let thisIsaveryLONGVariableThatRecordsPlayerscore345654 = 0;

let s = d/t;
</pre>

<div class="notecard note">
<p><strong>Note</strong>: The only place where it is OK to not use human-readable semantic names is where a very common recognized convention exists, such as using <code>i</code>, <code>j</code>, etc. for loop iterators.</p>
</div>

<h3 id="Declaring_variables">Declaring variables</h3>

* **NOTE**: Do not use `let` if IE11 support is required.

<p>When declaring variables and constants, use the <code><a href="/en-US/docs/Web/JavaScript/Reference/Statements/let">let</a></code> and <code><a href="/en-US/docs/Web/JavaScript/Reference/Statements/const">const</a></code> keywords, not <code><a href="/en-US/docs/Web/JavaScript/Reference/Statements/var">var</a></code>.</p>

<p>If a variable will not be reassigned, prefer <code>const</code>:</p>

<pre class="brush: js example-good notranslate">const myName = 'Chris';
console.log(myName);
</pre>

<p>Otherwise, use <code>let</code>:</p>

<pre class="brush: js example-good notranslate">let myAge = '40';
myAge++;
console.log('Happy birthday!');
</pre>

<p>This example uses <code>let</code> where it should prefer <code>const</code>. It will work but should be avoided in MDN code examples:</p>

<pre class="brush: js example-bad notranslate">let myName = 'Chris';
console.log(myName);
</pre>

<p>This example uses const for a variable that gets reassigned. The reassignment will throw an error:</p>

<pre class="brush: js example-bad notranslate">const myAge = '40';
myAge++;
console.log('Happy birthday!');
</pre>

<p>This example uses <code>var</code>, which should be avoided in MDN code examples unless it is really needed:</p>

<pre class="brush: js example-bad notranslate">var myAge = '40';
var myName = 'Chris';</pre>

<h2 id="Operators_and_comparison">Operators and comparison</h2>

<h3 id="Ternary_operators">Ternary operators</h3>

<p>Ternary operators should be put on a single line:</p>

<pre class="brush: js example-good notranslate">let status = (age &gt;= 18) ? 'adult' : 'minor';</pre>

<p>Not nested:</p>

<pre class="brush: js example-bad notranslate">let status = (age &gt;= 18)
  ? 'adult'
  : 'minor';</pre>

<p>This is much harder to read.</p>

<h3 id="Use_strict_equality">Use strict equality</h3>

<p>Always use strict equality and inequality.</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">name === 'Chris';
age !== 25;</pre>

<p>Not this:</p>

<pre class="brush: js example-bad notranslate">name == 'Chris';
age != 25;</pre>

<h3 id="Use_shortcuts_for_boolean_tests">Use shortcuts for boolean tests</h3>

<p>Use shortcuts for boolean tests — use <code>x</code> and <code>!x</code>, not <code>x === true</code> and <code>x === false</code>.</p>

<h2 id="Control_statements">Control statements</h2>

<p>Write control statements like this:</p>

<pre class="brush: js example-bad notranslate">if (iceCream) {
  alert('Woo hoo!');
}</pre>

<p>Not this:</p>

<pre class="brush: js example-good notranslate">if(iceCream){
  alert('Woo hoo!');
}</pre>

<p>Also bear in mind:</p>

<ul>
 <li>There should be <em>a space</em> between a control statement keyword and its opening parenthesis.</li>
 <li>There should be <em>a space</em> between the parentheses and the opening curly brace.</li>
</ul>

<h2 id="Strings">Strings</h2>

<h3 id="Use_template_literals">Use template literals</h3>

* **NOTE**: Do not use template literals if IE11 support is required.

<p>For inserting values into strings, use string literals.</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">let myName = 'Chris';
console.log(`Hi! I'm ${myName}!`);</pre>

<p>Not this:</p>

<pre class="brush: js example-bad notranslate">let myName = 'Chris';
console.log('Hi! I\'m' + myName + '!');</pre>

<h2 id="Conditionals">Conditionals</h3>

<h3 id="Switch_statements">Switch statements</h3>

<p>Format switch statements like this:</p>

<pre class="brush: js example-good notranslate">let expr = 'Papayas';
switch(expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Papayas':
    console.log('Mangoes and papayas are $2.79 a pound.');
    // expected output: "Mangoes and papayas are $2.79 a pound."
    break;
  default:
    console.log('Sorry, we are out of ' + expr + '.');
}</pre>

<h2 id="Functions_and_objects">Functions and objects</h2>

<h3 id="Function_naming">Function naming</h3>

<p>For function names use lowerCamelCasing, and use concise, human-readable, semantic names where appropriate.</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">function sayHello() {
  alert('Hello!');
};</pre>

<p>Not these:</p>

<pre class="brush: js example-bad notranslate">function SayHello() {
  alert('Hello!');
};

function notVeryObviousName() {
  alert('Hello!');
};
</pre>

<div class="notecard note">
<p><strong>Note</strong>: The only place where it is OK to not use human-readable semantic names is where a very common recognized convention exists, such as using <code>i</code>, <code>j</code>, etc. for loop iterators.</p>
</div>

<h3 id="Defining_functions">Defining functions</h3>

<p>Where possible, use the <code>function</code> declaration to define functions over function expressions:</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">function sum(a, b) {
  return a + b;
}</pre>

<p>Not this:</p>

<pre class="brush: js example-bad notranslate">let sum = function(a, b) {
  return a + b;
}</pre>

<p>When using anonymous functions inside a method that requires a function as a parameter, it is acceptable (although not required) to use an arrow function to make the code shorter and cleaner.</p>

<p>So instead of this:</p>

<pre class="brush: js example-good notranslate">const array1 = [1, 2, 3, 4];
let sum = array.reduce(function(a, b) {
  return a + b;
});</pre>

<p>you could write this:</p>

<pre class="brush: js example-good notranslate">const array = [1, 2, 3, 4];
let sum = array.reduce((a, b) =&gt;
  a + b
);</pre>

<p>Also bear in mind:</p>

<ul>
 <li>There should be <em>no space</em> between a function name and its opening parenthesis.</li>
 <li>There should be <em>a space</em> between the parentheses and the opening curly brace.</li>
</ul>

<h3 id="Creating_objects">Creating objects</h3>

<p>Use literals — not constructors — for creating general objects (i.e., when classes are not involved):</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">let myObject = { };
</pre>

<p>Not this:</p>

<pre class="brush: js example-bad notranslate">let myObject = new Object();
</pre>

<h3 id="Object_classes">Object classes</h3>

<p>Use ES class syntax for objects, not old-style constructors.</p>

<p>For example:</p>

<pre class="brush: js example-good notranslate">class Person {
  constructor(name, age, gender) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }

  greeting() {
    console.log(`Hi! I'm ${this.name}`);
  };
}</pre>

<p>Use <code>extends</code> for inheritance:</p>

<pre class="brush: js example-good notranslate">class Teacher extends Person {
  ...
}</pre>

<h3 id="Object_naming">Object naming</h3>

<p>When defining an object class (as seen above), use UpperCamelCasing (also known as PascalCasing) for the class name, and lowerCamelCasing for the object property and method names.</p>

<p>When defining an object instance, either a literal or via a constructor, use lowerCamelCase for the instance name:</p>

<pre class="brush: js example-good notranslate">let hanSolo = new Person('Han Solo', 25, 'male');

let hanSolo = {
  name: 'Han Solo',
  age: 25,
  gender: 'male'
}</pre>

<h2 id="Arrays">Arrays</h2>

<h3 id="Creating_arrays">Creating arrays</h3>

<p>Use literals — not constructors — for creating arrays:</p>

<p>Do this:</p>

<pre class="brush: js example-good notranslate">let myArray = [ ];</pre>

<p>Not this:</p>

<pre class="brush: js example-bad notranslate">let myArray = new Array(length);</pre>

<h2 id="Error_handling">Error handling</h2>

<p>If certain states of your program throw uncaught errors, they will halt execution and potentially reduce the usefulness of the example. You should therefore catch errors using a <code><a href="/en-US/docs/Web/JavaScript/Reference/Statements/try...catch">try...catch</a></code> block:</p>

<pre class="brush: js example-good notranslate">try {
  console.log(results);
}
catch(e) {
  console.error(e);
}</pre>
