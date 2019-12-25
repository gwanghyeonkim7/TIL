### **12/24**

***

<h4> html 사용할 때 String 을 가장 많이 사용

@Controller 

public class HtmlController { 	

​	@GetMapping("html/string") 

​	public String html() { return "html/string"; }



** Json을 사용할 때는 @ResponseBody만 추가!

**Controller를 RestController로 바꾸면 ResponseBody를 사용하지

않고도 Json의 형태를 사용 가능



### 응답

- HTML : String, Map, void .....

- JONS : 복합 데이터 + @ResponseBody

  ​		또는 복합 데이터 + @ResponseBody

### 요청

- @RequestParam : ? Controller Method의 인자명과 동일
- @ModelAttribute : Model Class의 변수명과 동일



### HTTP

- Hyper Text Transfer Protocol {Secure]
  - 절대 상태를 기억하지 않는다. stateless







Client 쪽이 쿠키 >>>>> Server 쪽이 세션



### AOP : 관점 지향 프로그램

<h4> Aspect Oriented Programming

**Transaction : 더 넓은, 많은 범위를 이용하기 위해서 사용.

IoC/DI : Inversion of Control / Dependency Injection)





### ControllerAdvice

- Controller에서 발생되는 오류를 감지하고 처리해주는 기능



<h5> AOP : 어떤한 클래스든, 어떠한 매소드든 대상
    > 스프링의 기능

<h5> Filter : 접속하는 주소(url)를 대상
    > 자바의 고유기능
<h5> Intercepter : 접속하는 주소(url)를 대상   
    > 스프링의 기능



