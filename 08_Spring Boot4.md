### 12/27

***

- C -  Create
- R - Read (Retrieve)
- U - Update
- D - Delete





NullPointer - 만들어지지 않을 것을 사용할 때 나옴.



Spring boot

- RestTemplate
- JSON Parsing



Java

- Scanner를 이용한 입력
- 입력된 자료를 클래스로 저장

~~~java
public calss Test {
    // main 입력 후 Ctrl + Space
    public static void main(String[] args) { 
    	// syso 입력 후 Ctrl + Space
    	System.out.println("입력해주세요.");
    	Scanner s = new Scanner(Systmem.in);
    	// 입력 메소드 다양하게 존재
        int price = s.nextInt(); // 숫자 입력
    	String tile = s.next(); // 문자열 입력(줄바꿈 문자인 역슬레시n 포함)
    	String = s.nextLine(); // 문자열 입력 (역슬레시n 생략)}
}
  	// 클래스로 저장(담아주기)
    상품p = new 상품();
    //p.price = price; X
    p.setPrice(price); O
   
        
        p.title = title;
    p.category = category;
    System.out.println(p);
}
}
class 상품 {
    int price;
    String title;
    String category;
    
    // 우클릭 소스 게터세터 체크체체크
    
    @Override
    public String toString() {
        return "price : " + price + ", title : " + title
    }
    
    
}
~~~







Spring boot 

Json 형태를 html로 뿌려기