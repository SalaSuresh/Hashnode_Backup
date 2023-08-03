---
title: "Coupling"
datePublished: Tue Aug 01 2023 06:07:34 GMT+0000 (Coordinated Universal Time)
cuid: clkrwdgc8000509ml9qlrckhk
slug: coupling
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/-T6vP7ZGz0Q/upload/591d76380d115ecfcd6df7d7d0b9a321.jpeg
tags: programming-languages, programming-tips, coupling

---

Coupling is the measure of the degree of interdependence between the modules. Good software will have low coupling.

A software project will be developed module-wise, and all modules are dependent on each other. So coupling will denote the interdependence/relation between the modules of the software. To maintain good software, there should be less coupling between modules. **Loose Coupling makes it possible to:**

* Understand one class without reading others
    
* Change one class without effecting others
    
* Improves maintainability
    

*Example:*

`//Tightly Coupled`  
`class Volume {`  
 `public static void main(String args[]) {`  
  `Box b = new Box(5,5,5);`  
  `System.out.println(b.volume);`  
 `}`  
`}`  
`class Box {`  
 `public int volume;`  
 `Box(int length, int width, int height) {`  
  `this.volume = length * width * height;`  
 `}`  
`}`

`//Loosely Coupled`  
`class Volume {`  
 `public static void main(String args[]) {`  
  `Box b = new Box(5,5,5);`  
  `System.out.println(b.getVolume());`  
 `}`  
`}`  
`final class Box {`  
  `private int volume;`  
  `Box(int length, int width, int height) {`  
   `this.volume = length * width * height;`  
  `}`  
 `public int getVolume() {`  
  `return volume;`  
 `}`  
`}`

**Categories of Coupling:**

[![](https://1.bp.blogspot.com/-r4rvh3qxnRg/XpSrD5w2AiI/AAAAAAAAorI/d8gBOaEyVuoRbkRXOXAxS1vGepyiLxBRgCLcBGAsYHQ/s400/coupling_cat.png align="center")](https://www.blogger.com/blog/post/edit/8012847841869407757/1545338252026282564#)

**1) Data Coupling:** If the dependency between the modules is **based on the fact that they communicate by passing only data, then the modules are said to be data coupled**. In data coupling, the components are independent of each other and communicate through data. Module communications don’t contain tramp data.  
*Example:* Customer billing system.

`Class Student {`  
 `private String getStudentAddress() {`  
  `return database.returnAddress(getStudentId())`  
 `}`  
 `private int getStudentId() {`  
  `return sudentId;`  
 `}`  
`}`

**2) Stamp Coupling:** In stamp coupling, **the complete data structure is passed from one module to another module**. Therefore, it involves tramp data. It may be necessary due to efficiency factors- this choice made by the insightful designer, not a lazy programmer.  
*Example:*

`Class Company {`  
 `private String getUserAddress(Employee e) {`  
  `return e.getAddress();`  
 `}`  
`}`  
`class Employee {`  
 `private String name;`  
 `private String address;`  
 `private int id;`

 `//getters and setters...`

`}`

**3) Control Coupling:** **If the modules communicate by passing control information, then they are said to be control coupled**. It can be bad if parameters indicate completely different behavior and good if parameters allow factoring and reuse of functionality.  
*Example:* Sort function that takes comparison function as an argument.

`Class EvenNumber {`  
 `Array[] a = {1,3,4,5,7,8,9};`  
 `private Array[] getListOfEvenNumbers(a) {`  
  `Array[] b;`  
  `for(a) {`  
   `if(isEvenNumber()) {`  
    `b[i] = a[i];`  
   `}`  
  `}`  
 `private boolean isEvenNumber(int number) {`  
  `return number%2 == 0`  
 `}`  
`}`

**4) External Coupling:** In external coupling, the modules depend on other modules, external to the software being developed or to a particular type of hardware.  
Example: protocol, external file, device format, etc. H/w and S/W laptops and other company printers.

**5) Common Coupling:** The modules have shared data such as global data structures. The changes in global data mean tracing back to all modules which access that data to evaluate the effect of the change. So it has got disadvantages like difficulty in reusing modules, reduced ability to control data accesses and reduced maintainability.  
Example: Bank balance with ATM and Bank.

**6) Content Coupling:** In content coupling, one module can modify the data of another module or control flow is passed from one module to the other module. This is the worst form of coupling and should be avoided.  
Example:  
[https://stackoverflow.com/questions/27188180/what-is-content-coupling](https://www.blogger.com/blog/post/edit/8012847841869407757/1545338252026282564#)