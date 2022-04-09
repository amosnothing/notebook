## AOP 概念

AOP：Aspect Oriented Programming. 面向切面编程。与 OOP 面向对象编程相辅相成，OOP 以类为基本单元，而 AOP 则以 Aspect 切面为基本单元。

## 术语

- Aspect    
  通俗一点的理解，添加了 @Aspect 注解的类就是切面

- 连接点 Join point     
  在 Spring 中，它总是表示一个方法的执行

- Advice 通知   
  在切面的连接点采取的动作
    - 环绕通知
    - 前置通知
    - 后置通知
    - 异常通知
    - 返回通知

- 切入点 Point cut  
  一组匹配 Join point 的规则

- 目标对象  
  在 Spring 中通常是指被代理对象

- AOP 代理  
  Spring 中分为：基于接口的 jdk 动态代理和基于类的 cglib 代理

- 织入 Weaving  
  将增强应用到目标对象来创建代理对象的过程 

## 织入的三种时期

- 编译期

切面在目标类编译期间被织入

- 类加载期

切面在目标类加载到 JVM 期间被织入，需要特殊的类加载器，可以在目标类引入应用之前增强目标类的字节码

- 运行期

切面在应用运行期间被织入，一般 AOP 会给目标对象创建一个代理对象


## AOP 实现方式

### 静态织入

AspectJ: 一个采用 java 实现的 AOP 框架，能对代码进行编译，让代码具有 AspectJ 的 AOP 功能。在静态织入过程中，它的 acj 编译器会把 aspect 类编译成字节码后，再在 Java 目标类编译时织入，即先编译 aspect 类再编译目标类

### 动态代理

Spring Aop 通过动态代理技术实现的，而动态代理是基于反射设计的，Spring AOP 包括 jdk 动态代理和 cglib 动态代理
