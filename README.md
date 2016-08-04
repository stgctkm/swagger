# Swagger を Spring Boot で使うサンプル

## Swagger
http://swagger.io/

### 参考URL
http://heidloff.net/article/usage-of-swagger-2-0-in-spring-boot-applications-to-document-apis/

## 設定
build.gradle
```
dependencies {
	compile('io.springfox:springfox-swagger2:2.5.0')
	compile('io.springfox:springfox-swagger-ui:2.5.0')
}
```

Configration
```
@EnableSwagger2
@Configuration
public class SwaggerConfiguration {

    public Docket customDocklet() {
        return new Docket(DocumentationType.SWAGGER_2)
                .select()
                .apis(RequestHandlerSelectors.basePackage("com.example"))
                .build();
    }
}
```

## Swagger JSON
```
curl http://localhost:8080/v2/api-docs.json
```

## UI 
http://localhost:8080/swagger-ui.html