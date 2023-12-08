                                             
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
<img src="https://private-user-images.githubusercontent.com/1003805/288966214-2c06c84f-bf3c-4cea-a396-c8f58e46bb1e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDIwMTE4NDAsIm5iZiI6MTcwMjAxMTU0MCwicGF0aCI6Ii8xMDAzODA1LzI4ODk2NjIxNC0yYzA2Yzg0Zi1iZjNjLTRjZWEtYTM5Ni1jOGY1OGU0NmJiMWUucG5nP1gtQW16LUFsZ29yaXRobT1BV1M0LUhNQUMtU0hBMjU2JlgtQW16LUNyZWRlbnRpYWw9QUtJQUlXTkpZQVg0Q1NWRUg1M0ElMkYyMDIzMTIwOCUyRnVzLWVhc3QtMSUyRnMzJTJGYXdzNF9yZXF1ZXN0JlgtQW16LURhdGU9MjAyMzEyMDhUMDQ1OTAwWiZYLUFtei1FeHBpcmVzPTMwMCZYLUFtei1TaWduYXR1cmU9MzE0ZTE4N2VjOGE5Y2QzZTFjZDU3MDdkNTI5Y2I5NGU5NWRiMDYxODFkZTI0Zjg1MDk4ZmUxNDNhNGY0ZGYyNiZYLUFtei1TaWduZWRIZWFkZXJzPWhvc3QmYWN0b3JfaWQ9MCZrZXlfaWQ9MCZyZXBvX2lkPTAifQ.HhgYWwTWcLMrHZF6g7vO03X1ddiovVT_KKICLsHHjWY" alt="SOLID-interface segregation-principle" style="max-width: 100%;">

Ripu sudan Chauhan<br>
https://ripusudanchauhan.blogspot.com/<br>
https://ripusudan.github.io/<br>                                                  
https://www.linkedin.com/in/ripu-sudan-chauhan<br>

 
