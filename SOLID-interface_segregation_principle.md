                                             
# Realtime interface segregation principle example
---

## BAD CODE
```java
//An interface contaning technologies a developer can work

interface DeveloperInterface
{
 void workOnCSS();             //Frontend Technology
 void workOnJavascript();      //Frontend Technology
 void workOnHTML();            //Frontend Technology
 void workOnDB();              //Backend Technology
 void workOnBackEndLanguage(); //Backend Technology
}
```

```java
//FrontEndDeveloperClass  implemeting above interface ,some method he can not implement

class FrontEndDeveloperClass implements DeveloperInterface
{

  void workOnCSS(){
  //Yes I can work on CSS  😃
  }
  void workOnJavascript(){
  //Yes I can work on JS   😃
  }
  void workOnHTML(){
  //Yes I can work on HTML 😃
  }
  void workOnDB(){
  //NO I can not work on DB  😞
  }
  void workOnBackEndLanguage(){
  //NO I can not work on Back End Language  😞
  }

}
```
```java
//BackEndDeveloperClass  implemeting above interface ,some method he can not implement

class BackEndDeveloperClass implements DeveloperInterface
{

  void workOnCSS(){
  //NO I can not work on CSS 😞
  }
  void workOnJavascript(){
  //NO I can not work on JS  😞
  }
  void workOnHTML(){
  //NO I can not work on HTML 😞
  }
  void workOnDB(){
  //YES I can work on DB  😃
  }
  void workOnBackEndLanguage(){
  //YES I can work on Back End Language  😃
  }

}
```
___
## GOOD CODE

```java
//Segregate DeveloperInterface into FrontEndDeveloperInterface & BackEndDeveloperInterface

interface FrontEndDeveloperInterface
{
 void workOnCSS();             //Frontend Technology
 void workOnJavascript();      //Frontend Technology
 void workOnHTML();            //Frontend Technology 
}

interface BackEndDeveloperInterface
{
 void workOnDB();              //Backend Technology
 void workOnBackEndLanguage(); //Backend Technology
}
```

```java
class FrontEndDeveloperClass implements FrontEndDeveloperInterface
{

  void workOnCSS(){
  //Yes I can work on CSS  😃
  }
  void workOnJavascript(){
  //Yes I can work on JS   😃
  }
  void workOnHTML(){
  //Yes I can work on HTML 😃
  } 

}
```
```java
class BackEndDeveloperClass implements BackEndDeveloperInterface
{
 
  void workOnDB(){
  //YES I can work on DB  😃
  }
  void workOnBackEndLanguage(){
  //YES I can work on Back End Language  😃
  }

}
```
```java
class FullStackDeveloperClass implements FrontEndDeveloperInterface,BackEndDeveloperInterface {
  void workOnCSS(){
  //Yes I can work on CSS  😃
  }
  void workOnJavascript(){
  //Yes I can work on JS   😃
  }
  void workOnHTML(){
  //Yes I can work on HTML 😃
  } 
  void workOnDB(){
  //YES I can work on DB  😃
  }
  void workOnBackEndLanguage(){
  //YES I can work on Back End Language  😃
  }

}
```


Ripu sudan Chauhan<br>
https://ripusudanchauhan.blogspot.com/<br>
https://ripusudan.github.io/<br>                                                  
https://www.linkedin.com/in/ripu-sudan-chauhan<br>

 
