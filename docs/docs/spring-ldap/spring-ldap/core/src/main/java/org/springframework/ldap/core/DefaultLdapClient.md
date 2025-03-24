# 基础信息

|      |      |
|------|------|
| 名称 | DefaultLdapClient |
| 编码语言 | .java |
| 代码路径 | spring-ldap/core/src/main/java/org/springframework/ldap/core/DefaultLdapClient.java |
| 包名 | org.springframework.ldap.core |
| 依赖项 | ['java.util.ArrayList', 'java.util.Collections', 'java.util.Enumeration', 'java.util.List', 'java.util.NoSuchElementException', 'java.util.Objects', 'java.util.Spliterator', 'java.util.Spliterators', 'java.util.function.Consumer', 'java.util.function.Function', 'java.util.function.Supplier', 'java.util.stream.Stream', 'java.util.stream.StreamSupport', 'javax.naming.Binding', 'javax.naming.Name', 'javax.naming.NameClassPair', 'javax.naming.NameNotFoundException', 'javax.naming.NamingEnumeration', 'javax.naming.NamingException', 'javax.naming.PartialResultException', 'javax.naming.SizeLimitExceededException', 'javax.naming.directory.Attributes', 'javax.naming.directory.DirContext', 'javax.naming.directory.ModificationItem', 'javax.naming.directory.SearchControls', 'javax.naming.directory.SearchResult', 'javax.naming.ldap.LdapName', 'org.slf4j.Logger', 'org.slf4j.LoggerFactory', 'org.springframework.dao.EmptyResultDataAccessException', 'org.springframework.dao.IncorrectResultSizeDataAccessException', 'org.springframework.ldap.query.LdapQuery', 'org.springframework.ldap.query.LdapQueryBuilder', 'org.springframework.ldap.query.SearchScope', 'org.springframework.ldap.support.LdapUtils', 'org.springframework.util.Assert'] |
| 概述说明 | DefaultLdapClient实现LDAP操作，支持查询、认证、绑定及异常处理。 |

# 说明

DefaultLdapClient是一个用于实现LDAP操作的客户端工具，支持多种常见的LDAP功能，包括查询、认证和绑定等操作。该工具还具备异常处理机制，能够在操作过程中捕获并处理可能出现的错误，确保系统的稳定性和可靠性。通过DefaultLdapClient，用户可以方便地与LDAP服务器进行交互，执行各种管理任务，同时有效应对潜在的异常情况。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| DefaultLdapClient | class | DefaultLdapClient实现LDAP操作，支持查询、认证、绑定等，并处理异常。 |



## 类 DefaultLdapClient

|      |      |
|------|------|
| 访问范围 | None |
| 类型 | class |
| 名称 | DefaultLdapClient |
| 说明 | DefaultLdapClient实现LDAP操作，支持查询、认证、绑定等，并处理异常。 |


### UML类图

```mermaid
classDiagram
    class DefaultLdapClient {
        -Logger logger
        -boolean DONT_RETURN_OBJ_FLAG
        -boolean RETURN_OBJ_FLAG
        -Builder builder
        -ContextSource contextSource
        -Supplier~SearchControls~ searchControlsSupplier
        -boolean ignorePartialResultException
        -boolean ignoreNameNotFoundException
        -boolean ignoreSizeLimitExceededException
        +DefaultLdapClient(ContextSource contextSource, Supplier~SearchControls~ searchControlsSupplier, Builder builder)
        +ListSpec list(String name) ListSpec
        +ListSpec list(Name name) ListSpec
        +ListBindingsSpec listBindings(String name) ListBindingsSpec
        +ListBindingsSpec listBindings(Name name) ListBindingsSpec
        +SearchSpec search() SearchSpec
        +AuthenticateSpec authenticate() AuthenticateSpec
        +BindSpec bind(String name) BindSpec
        +BindSpec bind(Name name) BindSpec
        +ModifySpec modify(String name) ModifySpec
        +ModifySpec modify(Name name) ModifySpec
        +UnbindSpec unbind(String name) UnbindSpec
        +UnbindSpec unbind(Name name) UnbindSpec
        +Builder mutate() Builder
        +void setIgnorePartialResultException(boolean ignorePartialResultException)
        +void setIgnoreNameNotFoundException(boolean ignoreNameNotFoundException)
        +void setIgnoreSizeLimitExceededException(boolean ignoreSizeLimitExceededException)
        +~T~ computeWithReadOnlyContext(ContextExecutor~T~ executor) T
        +void runWithReadWriteContext(ContextRunnable runnable)
        -~T~ NamingExceptionFunction~Binding, T~ function(ContextMapper~T~ mapper)
        -~T~ NamingExceptionFunction~SearchResult, T~ function(AttributesMapper~T~ mapper)
        -~T~ Enumeration~T~ enumeration(NamingEnumeration~T~ enumeration)
        -Consumer~NamingException~ namingExceptionHandler
        -~S, T~ T toObject(NamingEnumeration~S~ results, NamingExceptionFunction~S, T~ mapper)
        -~S, T~ List~T~ toList(NamingEnumeration~S~ results, NamingExceptionFunction~S, T~ mapper)
        -~S, T~ Stream~T~ toStream(NamingEnumeration~S~ results, NamingExceptionFunction~S, T~ mapper)
        -void closeContext(DirContext ctx)
        -~T~ void closeNamingEnumeration(NamingEnumeration~T~ results)
    }

    class DefaultListSpec {
        -Name name
        +DefaultListSpec(Name name)
        +~T~ List~T~ toList(NameClassPairMapper~T~ mapper)
        +~T~ Stream~T~ toStream(NameClassPairMapper~T~ mapper)
    }

    class DefaultListBindingsSpec {
        -Name name
        +DefaultListBindingsSpec(Name name)
        +~T~ List~T~ toList(NameClassPairMapper~T~ mapper)
        +~T~ List~T~ toList(ContextMapper~T~ mapper)
        +~T~ Stream~T~ toStream(NameClassPairMapper~T~ mapper)
        +~T~ Stream~T~ toStream(ContextMapper~T~ mapper)
    }

    class DefaultAuthenticateSpec {
        -LdapClient.SearchSpec search
        -char[] password
        +AuthenticateSpec query(LdapQuery query)
        +AuthenticateSpec password(String password)
        +void execute()
        +~T~ T execute(AuthenticatedLdapEntryContextMapper~T~ mapper)
    }

    class DefaultSearchSpec {
        -LdapQuery query
        -SearchControls controls
        +SearchSpec name(String name)
        +SearchSpec name(Name name)
        +SearchSpec query(Consumer~LdapQueryBuilder~ consumer)
        +SearchSpec query(LdapQuery query)
        +~T~ T toObject(ContextMapper~T~ mapper)
        +~T~ T toObject(AttributesMapper~T~ mapper)
        +~T~ List~T~ toList(ContextMapper~T~ mapper)
        +~T~ List~T~ toList(AttributesMapper~T~ mapper)
        +~T~ Stream~T~ toStream(ContextMapper~T~ mapper)
        +~T~ Stream~T~ toStream(AttributesMapper~T~ mapper)
        -NamingEnumeration~SearchResult~ search(DirContext ctx)
        -SearchControls searchControlsForQuery(boolean returnObjFlag)
    }

    class DefaultBindSpec {
        -Name name
        -Object obj
        -Attributes attributes
        -boolean rebind
        +DefaultBindSpec(Name name)
        +BindSpec object(Object obj)
        +BindSpec attributes(Attributes attributes)
        +BindSpec replaceExisting(boolean replaceExisting)
        +void execute()
    }

    class DefaultModifySpec {
        -DirContextOperations entry
        -Name name
        -ModificationItem[] items
        +DefaultModifySpec(DirContextOperations entry)
        +ModifySpec name(String name)
        +ModifySpec name(Name name)
        +ModifySpec attributes(ModificationItem... modifications)
        +void execute()
    }

    class DefaultUnbindSpec {
        -Name name
        -boolean recursive
        +DefaultUnbindSpec(Name name)
        +UnbindSpec recursive(boolean recursive)
        +void execute()
        -void unbindRecursive(DirContext ctx, Name name)
    }

    interface LdapClient {
        <<Interface>>
        +ListSpec list(String name)
        +ListSpec list(Name name)
        +ListBindingsSpec listBindings(String name)
        +ListBindingsSpec listBindings(Name name)
        +SearchSpec search()
        +AuthenticateSpec authenticate()
        +BindSpec bind(String name)
        +BindSpec bind(Name name)
        +ModifySpec modify(String name)
        +ModifySpec modify(Name name)
        +UnbindSpec unbind(String name)
        +UnbindSpec unbind(Name name)
        +Builder mutate()
    }

    interface ContextRunnable {
        <<Interface>>
        +void run(DirContext ctx)
    }

    interface NamingExceptionFunction~S, T~ {
        <<Interface>>
        +T apply(S element)
        +Function~S, T~ wrap(Consumer~NamingException~ handler)
    }

    DefaultLdapClient --> LdapClient : 实现
    DefaultListSpec --> DefaultLdapClient : 依赖
    DefaultListBindingsSpec --> DefaultLdapClient : 依赖
    DefaultAuthenticateSpec --> DefaultLdapClient : 依赖
    DefaultSearchSpec --> DefaultLdapClient : 依赖
    DefaultBindSpec --> DefaultLdapClient : 依赖
    DefaultModifySpec --> DefaultLdapClient : 依赖
    DefaultUnbindSpec --> DefaultLdapClient : 依赖
    ContextRunnable --> DefaultLdapClient : 依赖
    NamingExceptionFunction --> DefaultLdapClient : 依赖
```

**描述：**  
`DefaultLdapClient` 是一个实现了 `LdapClient` 接口的类，提供了对 LDAP 目录服务的各种操作，如查询、认证、绑定、修改和删除等。该类通过多个内部类（如 `DefaultListSpec`、`DefaultSearchSpec` 等）来实现具体的操作逻辑，并使用了 `ContextSource` 和 `SearchControls` 等依赖项来管理 LDAP 连接和搜索控制。`DefaultLdapClient` 还处理了多种异常情况，如 `PartialResultException`、`NameNotFoundException` 等，确保操作的健壮性。


### 内部方法调用关系图

```mermaid
graph TD
    A["类DefaultLdapClient"]
    B["属性: Logger logger"]
    C["属性: boolean DONT_RETURN_OBJ_FLAG"]
    D["属性: boolean RETURN_OBJ_FLAG"]
    E["属性: Builder builder"]
    F["属性: ContextSource contextSource"]
    G["属性: Supplier<SearchControls> searchControlsSupplier"]
    H["属性: boolean ignorePartialResultException"]
    I["属性: boolean ignoreNameNotFoundException"]
    J["属性: boolean ignoreSizeLimitExceededException"]
    K["构造方法: DefaultLdapClient(ContextSource, Supplier<SearchControls>, Builder)"]
    L["方法: ListSpec list(String name)"]
    M["方法: ListSpec list(Name name)"]
    N["方法: ListBindingsSpec listBindings(String name)"]
    O["方法: ListBindingsSpec listBindings(Name name)"]
    P["方法: SearchSpec search()"]
    Q["方法: AuthenticateSpec authenticate()"]
    R["方法: BindSpec bind(String name)"]
    S["方法: BindSpec bind(Name name)"]
    T["方法: ModifySpec modify(String name)"]
    U["方法: ModifySpec modify(Name name)"]
    V["方法: UnbindSpec unbind(String name)"]
    W["方法: UnbindSpec unbind(Name name)"]
    X["方法: Builder mutate()"]
    Y["方法: void setIgnorePartialResultException(boolean)"]
    Z["方法: void setIgnoreNameNotFoundException(boolean)"]
    AA["方法: void setIgnoreSizeLimitExceededException(boolean)"]
    AB["方法: <T> T computeWithReadOnlyContext(ContextExecutor<T>)"]
    AC["方法: void runWithReadWriteContext(ContextRunnable)"]
    AD["方法: private <T> NamingExceptionFunction<? extends Binding, T> function(ContextMapper<T>)"]
    AE["方法: private <T> NamingExceptionFunction<? extends SearchResult, T> function(AttributesMapper<T>)"]
    AF["方法: private <T> Enumeration<T> enumeration(NamingEnumeration<T>)"]
    AG["方法: private final Consumer<NamingException> namingExceptionHandler"]
    AH["方法: private <S extends NameClassPair, T> T toObject(NamingEnumeration<S>, NamingExceptionFunction<? super S, T>)"]
    AI["方法: private <S extends NameClassPair, T> List<T> toList(NamingEnumeration<S>, NamingExceptionFunction<? super S, T>)"]
    AJ["方法: private <S extends NameClassPair, T> Stream<T> toStream(NamingEnumeration<S>, NamingExceptionFunction<? super S, T>)"]
    AK["方法: private void closeContext(DirContext)"]
    AL["方法: private <T> void closeNamingEnumeration(NamingEnumeration<T>)"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    A --> I
    A --> J
    A --> K
    A --> L
    A --> M
    A --> N
    A --> O
    A --> P
    A --> Q
    A --> R
    A --> S
    A --> T
    A --> U
    A --> V
    A --> W
    A --> X
    A --> Y
    A --> Z
    A --> AA
    A --> AB
    A --> AC
    A --> AD
    A --> AE
    A --> AF
    A --> AG
    A --> AH
    A --> AI
    A --> AJ
    A --> AK
    A --> AL
```

这段代码定义了一个名为 `DefaultLdapClient` 的类，它实现了 `LdapClient` 接口。该类主要用于处理与 LDAP 服务器的交互，包括列表、搜索、认证、绑定、修改和解绑等操作。代码中包含了多个内部类和方法，用于处理不同的 LDAP 操作和异常情况。`DefaultLdapClient` 类通过 `ContextSource` 和 `SearchControls` 供应商来管理 LDAP 上下文和搜索控制，并通过多个布尔标志来控制是否忽略特定的异常。代码结构清晰，功能模块化，便于扩展和维护。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| builder | Builder | 私有不可变的Builder实例。 |
| contextSource | ContextSource | 私有常量上下文源实例。 |
| ignoreNameNotFoundException = false | boolean | 忽略名称未找到异常。 |
| DONT_RETURN_OBJ_FLAG = false | boolean | 静态布尔常量DONT_RETURN_OBJ_FLAG值为false。 |
| ignorePartialResultException = false | boolean | 忽略部分结果异常的布尔变量设为false。 |
| RETURN_OBJ_FLAG = true | boolean | 定义私有静态常量RETURN_OBJ_FLAG，值为true。 |
| logger = LoggerFactory.getLogger(DefaultLdapClient.class) | Logger | 定义私有日志记录器，用于DefaultLdapClient类。 |
| ignoreSizeLimitExceededException = true | boolean | 忽略大小限制异常设为真。 |
| searchControlsSupplier | Supplier<SearchControls> | 私有成员，提供SearchControls实例的Supplier接口。 |
| namingExceptionHandler = (ex) -> {		if (ex instanceof NameNotFoundException) {			if (!this.ignoreNameNotFoundException) {				throw LdapUtils.convertLdapException(ex);			}			this.logger.warn("Base context not found, ignoring: " + ex.getMessage());			return;		}		if (ex instanceof PartialResultException) {			// Workaround for AD servers not handling referrals correctly.			if (!this.ignorePartialResultException) {				throw LdapUtils.convertLdapException(ex);			}			this.logger.debug("PartialResultException encountered and ignored", ex);			return;		}		if (ex instanceof SizeLimitExceededException) {			if (!this.ignoreSizeLimitExceededException) {				throw LdapUtils.convertLdapException(ex);			}			this.logger.debug("SizeLimitExceededException encountered and ignored", ex);			return;		}		throw LdapUtils.convertLdapException(ex);	} | Consumer<NamingException> | 处理LDAP命名异常，忽略特定异常并记录日志，否则抛出转换后的异常。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| search | SearchSpec | 重写search方法，返回DefaultSearchSpec实例。 |
| setIgnorePartialResultException | void | 设置忽略部分结果异常的布尔值。 |
| closeContext | void | 关闭DirContext对象，忽略异常。 |
| mutate | Builder | 重写Builder类的mutate方法，返回当前builder实例。 |
| list | ListSpec | 重写list方法，返回基于名称的DefaultListSpec实例。 |
| computeWithReadOnlyContext | T | 方法使用只读上下文执行任务，处理异常并关闭上下文。 |
| closeNamingEnumeration | void | 关闭非空NamingEnumeration对象，忽略异常。 |
| list | ListSpec | 重写list方法，返回DefaultListSpec实例。 |
| function | NamingExceptionFunction<? extends Binding, T> | 定义私有泛型函数，通过上下文映射器转换结果对象。 |
| listBindings | ListBindingsSpec | 重写方法listBindings，返回DefaultListBindingsSpec实例。 |
| setIgnoreSizeLimitExceededException | void | 设置是否忽略大小限制超出的异常。 |
| setIgnoreNameNotFoundException | void | 设置是否忽略名称未找到异常。 |
| unbind | UnbindSpec | 重写unbind方法，返回基于指定名称的DefaultUnbindSpec实例。 |
| function | NamingExceptionFunction<? extends SearchResult, T> | 私有方法返回NamingExceptionFunction，映射SearchResult到T类型。 |
| runWithReadWriteContext | void | 使用读写上下文执行任务，处理异常并关闭上下文。 |
| listBindings | ListBindingsSpec | 该方法返回一个基于指定名称的默认绑定列表规范。 |
| toList | List<T> | 将NamingEnumeration转换为List，应用映射函数并处理异常。 |
| modify | ModifySpec | 重写modify方法，返回基于指定名称的DefaultModifySpec实例。 |
| modify | ModifySpec | 重写modify方法，返回基于DirContextAdapter的DefaultModifySpec实例。 |
| authenticate | AuthenticateSpec | 重写authenticate方法，返回DefaultAuthenticateSpec实例。 |
| bind | BindSpec | 重写bind方法，使用Name参数创建DefaultBindSpec实例。 |
| enumeration | Enumeration<T> | 将NamingEnumeration转换为Enumeration，处理异常并返回元素。 |
| bind | BindSpec | 重写bind方法，返回包含LDAP名称的DefaultBindSpec实例。 |
| toStream | Stream<T> | 将NamingEnumeration转换为Stream，处理异常并过滤非空值，最后关闭枚举。 |
| unbind | UnbindSpec | 重写unbind方法，返回基于LdapName的DefaultUnbindSpec实例。 |
| toObject | T | 私有方法将NamingEnumeration转换为对象，处理异常并确保结果唯一。 |




