softwares required :

VS code
NodeJS

Jvascript: 
scripting language, 
loosely typed, 
concept of datatypes is decided based on runtime literal value,
Event based callbacks(effects),
Single threaded:
Event Loop waits and gets the events in Q to put in stack
APi registaration- callbacks registered
Stack- functions loaded
Event Q

Runs on JsEngine:
-V8 engine used in chrome and nodejs
-Spider monkey
-Adobe
-Chakra, continnum-MS
Nashorn-Oracle, Java

Javscript can run where these engines are available. both server and client side anywhere


All Engines by default support ES5- EXMA script 5 version of JS

Hoisted in JS : variable declaretion moves to top of the function
			Var b= 10 = var b; b=10
if not having var ex c = 10;c can be accessed anywhere.
Hoisting: functon scope , Global scope(without var)

Good practice : "use Strict" will no allow implicit; c=20 is error

types 
: undifiened, number ,string, aboolean object, null,
JS has ";" insersion

return
{
}
objects in JS
using Objects: ara 

Prototype : info should be avalialbe only in a prottype not in each objects, used for class function.
Person.Prototype.GetDetails



JSON 
var obj = {}
var p ={
id : "abc",
name: "1232edsa"
}

Bind
Call
Apply

Functional Style of Programing

High order functons:
Functions that accepts other functons as aurgment,
functions that retrun funiton
RXjs marbel

Closure in Javascript function returning a function: 

-------------------------------------------
ES6 =ECMA sript 2015 => ES 2015
ES7 = ESNext

most of the engines are yet to support these version, so we use transpiler to convert ES6/7 to lower version.

ex transpiler : Babel, Traucer

ES6 features:
1. Scope
new kwywords : let and const to introduce scope members
let for a blocked level varables.
2. Arrow operators and default values
 let add = (x,y) => {return x+y;}
let sub = (x,y) => x-y
2.New string litleral ``
var name = "smith";
var msg =`
this is first line 
name is ${name}
`
3. Deconstructing:
a) arrays
 var colors=["red","blue"]
old: colors[2]
new: var [r,g,b...others] = colors
console.log(g)/blue

b) Object
var p ={name:"guru", id: 1, price : 23123}
old
p.id
p["name"]
new :
 var {name,id} = p
console.log(name)


4.refernce :
let r = ob//refence
copy
let r = {...ob}//copy

5. Class
6. Promise API : ASync methods
   resolved, rejected error

Syncro: 
Dotask()
let res = dotask()
console.log("done")//code is blocked till do task is completed

Async:
funcion dotask()
dotask.then(funciton(Data){},function(ref){}).catch(err){}


Node JS: 
PRovides Javascript environments on top of V8 engine
what can i use Node js for:
a. to write server side javascript code-
	build traditional web application like
	-Asp,net
	-servlet asd JSP
	It gives view templates like pug, EJS,JADE
b. Build REST API's
C. Use as Environment to develop client side application like react angular Vue

Environment to convert devlopment code to brwoser: Browserify
browser needs ES5, you write code any verson ES6/7 then browsify in enverimment

Common thing we do in devlopemnt code before going to production
a. Trasnpile/complile
b.Minify
c.Uglify: smaller names ro functions and veriables
d.lint
e.run tests

npm i -g typescript
tsc --version


what ever in package .json will be installed by running npm install
object.DefinePRoerty


Angular : 9
RWD and SPA
RWD :Responsive web design : making page adjusted to diff resolution
		CSS 3 media queries
		Bootstrap
SPA : single page application 
will have onl on html page but many templates

Challanges faced in SPA: a)SPO(search engine optimization: solution:differnt templates will be loaded in same idex.html page)
			b)Browser history
			c) Security: Put gaurds to protect diff URI access
				     XSS- need to sanities before rendering
			d) Dependency Injection
For SPA we ahve following library framwork
a)Angular - google [ framework]
b)React --Facebook [template libraries]
c)Backbone
d)Vue

Client side rendering -Templates:
Jqueries
HandleBar #
Mustach {}
UnderScore _ 

Angular Building Blocks
Module - 
Component -Selector,template,css, state,behaviour
Templates
Services - Business logic, inteerect backend,restApi,
Router - Different URI differnt views
Gaurds
Pipe
Directive
Rouetes with Parameter

Service -Share data between componets which are independent.
@injectable:creates and onbject by its own/default singleton
Promise- cant cancel, you get and then filter
Observable :
can cancel, 
based on stream(map,filter,limit)(you can filter and get the data,
lazy(until u subscribe)
Observer desgin pattern: each observers  register/Subscribe to a subject
any 


name convention:[].[building block].ts //all in small










Angular.json file has entry to main.ts
main.ts bootsraps appModule
appMdoule loads components
	 loads services
 	 loads other dependent modules-import
	bootstraps app.component.ts

index.html
<app-root></app-root>


commands
npm i -g @angular/cli - to get ng
ng new customerapp to create app and all configs
npm i bootstrap font-awesome@4
ng g c customer/customers
npm i -g json-server
json-server --watch .\data.json --port 3000 --make sure u run in the path where data.json
npm install primeng primeicons chart.js @angular/animations // all angular 
npm install

ctl shift p find file

interface: model


Strcutural directives : * - modifies dom
Properties: [PropertieName] = "value"
taken as @input
Events()
[()] two way binding

from child to parent only events can go
top to bottom properties

http://github.com/banuPrakash/SG

Parent to Child: input
Child to Parent-event Output

Modules and Lazy loading: 
ForRoot-Onlyonce in the application.

CanActivate/CanDeactivate-Gaurds
Enabling/Disabling the Routes

@viewChild-get funtionality(behavoiur)  of widgets(other components)[parent to child]
in html anything with # is template variable and visible only template. good for forms

modules to modules-parent
parems are observable internally.


Subject-Observer/observaable
Service will not know when to subscribe
Providedin -Root-throughout applocaiton




import { Injectable } from '@angular/core';
import { HttpInterceptor, HttpHandler, HttpRequest, HttpEvent, HttpResponse }
  from '@angular/common/http';

import { Observable } from 'rxjs';
import 'rxjs/add/operator/tap';

@Injectable({
    providedIn: 'root'
})
export class MyInterceptor implements HttpInterceptor {
  intercept(
    req: HttpRequest<any>,
    next: HttpHandler
  ): Observable<HttpEvent<any>> {
    console.log(req);
    return next.handle(req) ;

  }
}
