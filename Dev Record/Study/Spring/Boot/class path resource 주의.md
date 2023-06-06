
ClassPathResource를 사용하여 resource를 불러와 사용하는 경우

```java

ClassPathResource resource = new ClassPahtResource("/test.properites");

resource.getFile(); //NullPointerExceptoin, IOException
```

파일형태로 resource를 불러와 사용하려는 경우 jar, war와 같이 배포된 상황에서 resource내에 있는 파일에