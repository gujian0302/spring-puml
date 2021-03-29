# resource-server 

## 配置相关

### 依赖

```
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-oauth2-resource-server</artifactId>
    </dependency>

```

### 开启方法级权限检查

```
@EnableReactiveMethodSecurity
public class Application {
  ....
}
```

### 内部实现解析

* ReactiveOAuth2ResourceServerAutoConfiguration: 响应式OAuth2资源服务器自动配置器
* org.springframework.boot.autoconfigure.security.oauth2.resource.OAuth2ResourceServerProperties: 资源服务器的jwt,opqauetoken properties
* org.springframework.boot.autoconfigure.security.oauth2.resource.reactive.ReactiveOAuth2ResourceServerConfiguration.JwtConfiguration: jwt需要加载的配置类
* org.springframework.boot.autoconfigure.security.oauth2.resource.reactive.ReactiveOAuth2ResourceServerJwkConfiguration.JwtConfiguration: 具体的加载jwt所需要的组件的类, JwtDecoder, SpringSecurityWebFilterChain。

#### org.springframework.security.config.web.server.ServerHttpSecurity#build

