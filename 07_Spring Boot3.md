



### 12 / 26

***

- Shift + Ctrl + R : 필요한 파일을 자동을 찾아줌.

모든 데이터는 고유한 값을 가진다. 



- @Controller @ Service @ Repository @Component
- 예외를 처리할 때 - (Exception e)









<h4> 파일 업로드

~~~java
package com.ggoreb.basic.controller;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.ResponseBody;
import org.springframework.web.multipart.MultipartFile;
import org.springframework.web.multipart.MultipartHttpServletRequest;
@Controller
public class UploadController {
@GetMapping("/upload1")
public String upload1() {
return "upload1";
}
@PostMapping("/upload1")
@ResponseBody
public String upload1Post(MultipartHttpServletRequest mRequest) {
String result = "";
MultipartFile mFile = mRequest.getFile("file");
String oName = mFile.getOriginalFilename();
result += oName + "\n";
return result;
}
}
~~~

<h4> templates/upload1.html

~~~java
<form method="post" enctype="multipart/form-data">
 <input type="file" name="file" multiple><br>
 <input type="submit" value="업로드">
</form>
~~~



<h4> application.properties

~~~java
# file upload
spring.servlet.multipart.max-file-size=2097152
spring.servlet.multipart.max-request-size=2097152
~~~









<h4> 파일 다운로드



~~~Java
package com.ggoreb.basic.controller;
import java.io.File;
import java.io.FileInputStream;
import java.net.URLEncoder;
import org.springframework.core.io.InputStreamResource;
import org.springframework.core.io.Resource;
import org.springframework.http.MediaType;
import org.springframework.http.ResponseEntity;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
@Controller
public class DownloadController {
 @GetMapping("/download")
 public ResponseEntity<Resource> download() throws Exception {
 File file = new File("f:/spring-boot-logo.png");
 InputStreamResource resource = new InputStreamResource(new FileInputStream(file));
 return ResponseEntity.ok()
 .header("content-disposition",
 "filename=" + URLEncoder.encode(file.getName(), "utf-8"))
 .contentLength(file.length())
 .contentType(MediaType.parseMediaType("application/octet-stream"))
 .body(resource);
 }
}
~~~



### 카카오 이용해서 만들기

<script src="http://code.jquery.com/jquery-3.1.1.min.js"></script>


{}가 나오면 Json



~~~java
@GetMapping("/getKakao")
	public ResponseEntity<Map> getKakao(
			@RequestParam("address") String address) {
		RestTemplate rt = new RestTemplate();
		RequestEntity requestEntity = null;
		try {
			requestEntity = RequestEntity
					.get(new URI("https://dapi.kakao.com/v2/local/search/address.json?query="
							+ URLEncoder.encode(address, "utf-8")))
					.header("Authorization", "KakaoAK d4be7b479f4b4cbd99bd19ae87f88b4b").build();
		} catch (UnsupportedEncodingException e) {
			e.printStackTrace();
		} catch (URISyntaxException e) {
			e.printStackTrace();
		}
		ResponseEntity<Map> entity = rt.exchange(requestEntity, Map.class);

		return entity;

	}
	
~~~





### 웹사이트 만들 때 기본적인 스프링 부트 기능

- Spring Boot DevTools

- Lombok

- Spring Data JPA

- H2 Database

- Thymeleaf

- Spring Web