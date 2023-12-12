##### invocation

``` kotlin
class TestCaseConfigTest: DescribeSpec({  
    describe("test case config"){  
        context("multiple run test case") {  
            it("run multiple time").config(invocations = 3) {  
                println("run multiple time")  
            }  
        }
    }
})
```

`invocation` 값으로 n번 실행


##### threads