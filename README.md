Spring Base64 Url Decoder
=========================

This annotation delivers a annotation and adds a [HandlerMethodArgumentResolver] to the [Spring] MVC framework.

Usage
-----

Annotate your parameters with the **@DecodedUrl** annotation in a MVC Controller according to this example:
 
``` java
@Controller
public class TestController {
  @RequestMapping("/test")
  public String test(@DecodedUrl URL url) {
    return url.toExternalForm();
  }
}
```

And register the **Base64DecodingArgumentResolver** in to your MVC context:

``` java
@Configuration
public class Web extends WebMvcConfigurerAdapter {
  @Override
  public void addArgumentResolvers(List<HandlerMethodArgumentResolver> argumentResolvers) {
    argumentResolvers.add(new UrlResolvingHandlerMethodArgumentResolver());
  }
}
```

License
-------
MIT

[Spring]:http://spring.io/
[HandlerMethodArgumentResolver]:http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/method/support/HandlerMethodArgumentResolver.html
