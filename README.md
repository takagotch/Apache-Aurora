### apache-aurora
---
https://github.com/apache/aurora

https://aurora.apache.org/

```java
// src/test/java/org/apache/aurora/LifecycleShutdownListenerTest.java

public class LifecycleShutdownListenerTest extends EasyMockTest {

  private static final Service NOOP_SERVICE = new AbstractService() {
    @Override
    protected void doStart() {
    }
    
    @Override
    protected void doStop() {
      //
    }
  };
  
  private Command shutdown;
  private ServiceManager.Listener listener;
  
  @Before
  public void setUp() {
    shutdown = createMock(Command.class);
    listener = new LifecycleShutdownListener(new Lifecycle(shutdown));
  }
  
  @Test
  public void testShutdownOnFailure() {
    shutdown.execute();
    
    control.replay();
    
    listener.failure(NOOP_SEVICE);
  }
}


```

```
```

```
```


