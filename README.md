# diff-btw-call-bind-apply

## Call( ): 
The call() method invokes a function with a given 'this' value and arguments provided one by one. This means that we can call any function, and explicitly specify what 'this' should reference within the calling function.
### Example:
var frnd1={fname:"naveen",lname:"krish"}
var frnd2={fname:"gopi",lname:"krishna"}
function invite(greet1, greet2){
console.log(greet1 + ' '+ this.frnd1 +' '+ this.lname +' ' + greet2);
}
invite.call(frnd1,'hey','how are u?');
invite.call(frnd2,'hey','how are u?');

## Apply( ): 
Invokes the function and allows you to pass in arguments as an array.
### Example:
var frnd1={fname:"naveen",lname:"krish"}
var frnd2={fname:"gopi",lname:"krishna"}
function invite(greet1, greet2){
console.log(greet1 + ' '+ this.frnd1 +' '+ this.lname +' ' + greet2);
}
invite.call(frnd1,['hey','how are u?']);
invite.call(frnd2,['hey','how are u?']);

## Bind(): 
returns a new function, allowing you to pass in an array and any number of arguments.
When we use the bind() method:
#### 1.The JS engine is creating a new invite instance and binding friend1 and friend2 as its 'this' variable. So basically it copies the invite function.
#### 2.After creating a copy of the invite function it is able to call inviteFriend1( ) and inviteFriend2( ), although it wasn’t on the friend1 and friend2 object initially. It will now recognizes its properties and its methods.

#### Call and apply are pretty interchangeable. Both execute the current function immediately. You need to decide whether it’s easier to send in an array or a comma separated list of arguments. Whereas Bind creates a new function that will have this set to the first parameter passed to bind().
### Example:
var frnd1={fname:"naveen",lname:"krish"}
var frnd2={fname:"gopi",lname:"krishna"}
function invite(greet1, greet2){
console.log(greet1 + ' '+ this.frnd1 +' '+ this.lname +' ' + greet2);
}

var invitefrnd1=invite.bind(frnd1);
var invitefrnd1=invite.bind(frnd2);

invite.call(frnd1,['hey','how are u?']);
invite.call(frnd2,['hey','how are u?']);
