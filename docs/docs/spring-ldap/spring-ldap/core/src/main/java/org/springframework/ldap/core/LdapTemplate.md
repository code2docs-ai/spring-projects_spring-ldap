# 基础信息

|      |      |
|------|------|
| 名称 | LdapTemplate |
| 编码语言 | .java |
| 代码路径 | spring-ldap/core/src/main/java/org/springframework/ldap/core/LdapTemplate.java |
| 包名 | org.springframework.ldap.core |
| 依赖项 | ['java.util.List', 'java.util.Objects', 'java.util.Spliterator', 'java.util.Spliterators', 'java.util.function.Function', 'java.util.stream.Stream', 'java.util.stream.StreamSupport', 'javax.naming.Binding', 'javax.naming.Name', 'javax.naming.NameClassPair', 'javax.naming.NameNotFoundException', 'javax.naming.NamingEnumeration', 'javax.naming.PartialResultException', 'javax.naming.SizeLimitExceededException', 'javax.naming.directory.Attributes', 'javax.naming.directory.DirContext', 'javax.naming.directory.ModificationItem', 'javax.naming.directory.SearchControls', 'javax.naming.directory.SearchResult', 'javax.naming.ldap.LdapName', 'org.slf4j.Logger', 'org.slf4j.LoggerFactory', 'org.springframework.beans.factory.InitializingBean', 'org.springframework.dao.EmptyResultDataAccessException', 'org.springframework.dao.IncorrectResultSizeDataAccessException', 'org.springframework.ldap.AuthenticationException', 'org.springframework.ldap.NamingException', 'org.springframework.ldap.UncategorizedLdapException', 'org.springframework.ldap.filter.Filter', 'org.springframework.ldap.odm.core.ObjectDirectoryMapper', 'org.springframework.ldap.odm.core.OdmException', 'org.springframework.ldap.odm.core.impl.DefaultObjectDirectoryMapper', 'org.springframework.ldap.query.LdapQuery', 'org.springframework.ldap.query.LdapQueryBuilder', 'org.springframework.ldap.support.LdapUtils', 'org.springframework.util.Assert', 'org.springframework.util.CollectionUtils'] |
| 概述说明 | LdapTemplate类实现LdapOperations接口，支持LDAP搜索、绑定和属性修改。 |

# 说明

LdapTemplate类实现了LdapOperations接口，提供了对LDAP（轻量级目录访问协议）的基本操作功能。该类支持多种常见的LDAP操作，包括搜索、绑定以及修改属性等。通过这些功能，开发者可以方便地与LDAP服务器进行交互，执行查询、认证和数据更新等任务。LdapTemplate的设计旨在简化LDAP操作的复杂性，提升开发效率。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| LdapTemplate | class | LdapTemplate类实现LdapOperations接口，提供LDAP操作功能，支持搜索、绑定、修改属性等操作。 |



## 类 LdapTemplate

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | LdapTemplate |
| 说明 | LdapTemplate类实现LdapOperations接口，提供LDAP操作功能，支持搜索、绑定、修改属性等操作。 |


### UML类图

```mermaid
classDiagram
    class LdapTemplate {
        -Logger LOG
        -boolean DONT_RETURN_OBJ_FLAG
        -boolean RETURN_OBJ_FLAG
        -String[] ALL_ATTRIBUTES
        -ContextSource contextSource
        -boolean ignorePartialResultException
        -boolean ignoreNameNotFoundException
        -boolean ignoreSizeLimitExceededException
        -int defaultSearchScope
        -int defaultTimeLimit
        -int defaultCountLimit
        -ObjectDirectoryMapper odm
        +LdapTemplate()
        +LdapTemplate(ContextSource contextSource)
        +void setContextSource(ContextSource contextSource)
        +ObjectDirectoryMapper getObjectDirectoryMapper()
        +void setObjectDirectoryMapper(ObjectDirectoryMapper odm)
        +ContextSource getContextSource()
        +void setIgnoreNameNotFoundException(boolean ignore)
        +boolean isIgnoreNameNotFoundException()
        +void setIgnorePartialResultException(boolean ignore)
        +boolean isIgnorePartialResultException()
        +void setIgnoreSizeLimitExceededException(boolean ignore)
        +boolean isIgnoreSizeLimitExceededException()
        +void setDefaultSearchScope(int defaultSearchScope)
        +int getDefaultSearchScope()
        +void setDefaultTimeLimit(int defaultTimeLimit)
        +int getDefaultTimeLimit()
        +void setDefaultCountLimit(int defaultCountLimit)
        +int getDefaultCountLimit()
        +void search(Name base, String filter, int searchScope, boolean returningObjFlag, NameClassPairCallbackHandler handler)
        +void search(String base, String filter, int searchScope, boolean returningObjFlag, NameClassPairCallbackHandler handler)
        +void search(Name base, String filter, SearchControls controls, NameClassPairCallbackHandler handler)
        +void search(String base, String filter, SearchControls controls, NameClassPairCallbackHandler handler)
        +void search(Name base, String filter, SearchControls controls, NameClassPairCallbackHandler handler, DirContextProcessor processor)
        +void search(String base, String filter, SearchControls controls, NameClassPairCallbackHandler handler, DirContextProcessor processor)
        +void search(SearchExecutor se, NameClassPairCallbackHandler handler, DirContextProcessor processor)
        +void search(SearchExecutor se, NameClassPairCallbackHandler handler)
        +void search(Name base, String filter, NameClassPairCallbackHandler handler)
        +void search(String base, String filter, NameClassPairCallbackHandler handler)
        +List~T~ search(Name base, String filter, int searchScope, String[] attrs, AttributesMapper~T~ mapper)
        +List~T~ search(String base, String filter, int searchScope, String[] attrs, AttributesMapper~T~ mapper)
        +List~T~ search(Name base, String filter, int searchScope, AttributesMapper~T~ mapper)
        +List~T~ search(String base, String filter, int searchScope, AttributesMapper~T~ mapper)
        +List~T~ search(Name base, String filter, AttributesMapper~T~ mapper)
        +List~T~ search(String base, String filter, AttributesMapper~T~ mapper)
        +List~T~ search(Name base, String filter, int searchScope, String[] attrs, ContextMapper~T~ mapper)
        +List~T~ search(String base, String filter, int searchScope, String[] attrs, ContextMapper~T~ mapper)
        +List~T~ search(Name base, String filter, int searchScope, ContextMapper~T~ mapper)
        +List~T~ search(String base, String filter, int searchScope, ContextMapper~T~ mapper)
        +List~T~ search(Name base, String filter, ContextMapper~T~ mapper)
        +List~T~ search(String base, String filter, ContextMapper~T~ mapper)
        +List~T~ search(String base, String filter, SearchControls controls, ContextMapper~T~ mapper)
        +List~T~ search(Name base, String filter, SearchControls controls, ContextMapper~T~ mapper)
        +List~T~ search(Name base, String filter, SearchControls controls, AttributesMapper~T~ mapper)
        +List~T~ search(String base, String filter, SearchControls controls, AttributesMapper~T~ mapper)
        +List~T~ search(String base, String filter, SearchControls controls, AttributesMapper~T~ mapper, DirContextProcessor processor)
        +List~T~ search(Name base, String filter, SearchControls controls, AttributesMapper~T~ mapper, DirContextProcessor processor)
        +List~T~ search(String base, String filter, SearchControls controls, ContextMapper~T~ mapper, DirContextProcessor processor)
        +List~T~ search(Name base, String filter, SearchControls controls, ContextMapper~T~ mapper, DirContextProcessor processor)
        +void list(String base, NameClassPairCallbackHandler handler)
        +void list(Name base, NameClassPairCallbackHandler handler)
        +List~T~ list(String base, NameClassPairMapper~T~ mapper)
        +List~T~ list(Name base, NameClassPairMapper~T~ mapper)
        +List~String~ list(Name base)
        +List~String~ list(String base)
        +void listBindings(String base, NameClassPairCallbackHandler handler)
        +void listBindings(Name base, NameClassPairCallbackHandler handler)
        +List~T~ listBindings(String base, NameClassPairMapper~T~ mapper)
        +List~T~ listBindings(Name base, NameClassPairMapper~T~ mapper)
        +List~String~ listBindings(String base)
        +List~String~ listBindings(Name base)
        +List~T~ listBindings(String base, ContextMapper~T~ mapper)
        +List~T~ listBindings(Name base, ContextMapper~T~ mapper)
        +T executeReadOnly(ContextExecutor~T~ ce)
        +T executeReadWrite(ContextExecutor~T~ ce)
        +Object lookup(Name dn)
        +Object lookup(String dn)
        +T lookup(Name dn, AttributesMapper~T~ mapper)
        +T lookup(String dn, AttributesMapper~T~ mapper)
        +T lookup(Name dn, ContextMapper~T~ mapper)
        +T lookup(String dn, ContextMapper~T~ mapper)
        +T lookup(Name dn, String[] attributes, AttributesMapper~T~ mapper)
        +T lookup(String dn, String[] attributes, AttributesMapper~T~ mapper)
        +T lookup(Name dn, String[] attributes, ContextMapper~T~ mapper)
        +T lookup(String dn, String[] attributes, ContextMapper~T~ mapper)
        +void modifyAttributes(Name dn, ModificationItem[] mods)
        +void modifyAttributes(String dn, ModificationItem[] mods)
        +void bind(Name dn, Object obj, Attributes attributes)
        +void bind(String dn, Object obj, Attributes attributes)
        +void unbind(Name dn)
        +void unbind(String dn)
        +void unbind(Name dn, boolean recursive)
        +void unbind(String dn, boolean recursive)
        +void rebind(Name dn, Object obj, Attributes attributes)
        +void rebind(String dn, Object obj, Attributes attributes)
        +void rename(Name oldDn, Name newD极


### 内部方法调用关系图

```mermaid
graph TD
    A["类LdapTemplate"]
    B["属性: Logger LOG"]
    C["属性: boolean DONT_RETURN_OBJ_FLAG"]
    D["属性: boolean RETURN_OBJ_FLAG"]
    E["属性: String[] ALL_ATTRIBUTES"]
    F["属性: ContextSource contextSource"]
    G["属性: boolean ignorePartialResultException"]
    H["属性: boolean ignoreNameNotFoundException"]
    I["属性: boolean ignoreSizeLimitExceededException"]
    J["属性: int defaultSearchScope"]
    K["属性: int defaultTimeLimit"]
    L["属性: int defaultCountLimit"]
    M["属性: ObjectDirectoryMapper odm"]
    N["构造方法: LdapTemplate()"]
    O["构造方法: LdapTemplate(ContextSource contextSource)"]
    P["方法: void setContextSource(ContextSource contextSource)"]
    Q["方法: ObjectDirectoryMapper getObjectDirectoryMapper()"]
    R["方法: void setObjectDirectoryMapper(ObjectDirectoryMapper odm)"]
    S["方法: ContextSource getContextSource()"]
    T["方法: void setIgnoreNameNotFoundException(boolean ignore)"]
    U["方法: boolean isIgnoreNameNotFoundException()"]
    V["方法: void setIgnorePartialResultException(boolean ignore)"]
    W["方法: boolean isIgnorePartialResultException()"]
    X["方法: void setIgnoreSizeLimitExceededException(boolean ignore)"]
    Y["方法: boolean isIgnoreSizeLimitExceededException()"]
    Z["方法: void setDefaultSearchScope(int defaultSearchScope)"]
    AA["方法: int getDefaultSearchScope()"]
    AB["方法: void setDefaultTimeLimit(int defaultTimeLimit)"]
    AC["方法: int getDefaultTimeLimit()"]
    AD["方法: void setDefaultCountLimit(int defaultCountLimit)"]
    AE["方法: int getDefaultCountLimit()"]
    AF["方法: void search(Name base, String filter, int searchScope, boolean returningObjFlag, NameClassPairCallbackHandler handler)"]
    AG["方法: void search(String base, String filter, int searchScope, boolean returningObjFlag, NameClassPairCallbackHandler handler)"]
    AH["方法: void search(Name base, String filter, SearchControls controls, NameClassPairCallbackHandler handler)"]
    AI["方法: void search(String base, String filter, SearchControls controls, NameClassPairCallbackHandler handler)"]
    AJ["方法: void search(Name base, String filter, SearchControls controls, NameClassPairCallbackHandler handler, DirContextProcessor processor)"]
    AK["方法: void search(String base, String filter, SearchControls controls, NameClassPairCallbackHandler handler, DirContextProcessor processor)"]
    AL["方法: void search(SearchExecutor se, NameClassPairCallbackHandler handler, DirContextProcessor processor)"]
    AM["方法: void search(SearchExecutor se, NameClassPairCallbackHandler handler)"]
    AN["方法: void search(Name base, String filter, NameClassPairCallbackHandler handler)"]
    AO["方法: void search(String base, String filter, NameClassPairCallbackHandler handler)"]
    AP["方法: List<T> search(Name base, String filter, int searchScope, String[] attrs, AttributesMapper<T> mapper)"]
    AQ["方法: List<T> search(String base, String filter, int searchScope, String[] attrs, AttributesMapper<T> mapper)"]
    AR["方法: List<T> search(Name base, String filter, int searchScope, AttributesMapper<T> mapper)"]
    AS["方法: List<T> search(String base, String filter, int searchScope, AttributesMapper<T> mapper)"]
    AT["方法: List<T> search(Name base, String filter, AttributesMapper<T> mapper)"]
    AU["方法: List<T> search(String base, String filter, AttributesMapper<T> mapper)"]
    AV["方法: List<T> search(Name base, String filter, int searchScope, String[] attrs, ContextMapper<T> mapper)"]
    AW["方法: List<T> search(String base, String filter, int searchScope, String[] attrs, ContextMapper<T> mapper)"]
    AX["方法: List<T> search(Name base, String filter, int searchScope, ContextMapper<T> mapper)"]
    AY["方法: List<T> search(String base, String filter, int searchScope, ContextMapper<T> mapper)"]
    AZ["方法: List<T> search(Name base, String filter, ContextMapper<T> mapper)"]
    BA["方法: List<T> search(String base, String filter, ContextMapper<T> mapper)"]
    BB["方法: List<T> search(String base, String filter, SearchControls controls, ContextMapper<T> mapper)"]
    BC["方法: List<T> search(Name base, String filter, SearchControls controls, ContextMapper<T> mapper)"]
    BD["方法: List<T> search(Name base, String filter, SearchControls controls, AttributesMapper<T> mapper)"]
    BE["方法: List<T> search(String base, String filter, SearchControls controls, AttributesMapper<T> mapper)"]
    BF["方法: List<T> search(String base, String filter, SearchControls controls, AttributesMapper<T> mapper, DirContextProcessor processor)"]
    BG["方法: List<T> search(Name base, String filter, SearchControls controls, AttributesMapper<T> mapper, DirContextProcessor processor)"]
    BH["方法: List<T> search(String base, String filter, SearchControls controls, ContextMapper<T> mapper, DirContextProcessor processor)"]
    BI["方法: List<T> search(Name base, String filter, SearchControls controls, ContextMapper<T> mapper, DirContextProcessor processor)"]
    BJ["方法: void list(String base, NameClassPairCallbackHandler handler)"]
    BK["方法: void list(Name base, NameClassPairCallbackHandler handler)"]
    BL["方法: List<T> list(String base, NameClassPairMapper<T> mapper)"]
    BM["方法: List<T> list(Name base, NameClassPairMapper<T> mapper)"]
    BN["方法: List<String> list(Name base)"]
    BO["方法: List<String> list(String base)"]
    BP["方法: void listBindings(String base, NameClassPairCallbackHandler handler)"]
    BQ["方法: void listBindings(Name base, NameClassPairCallbackHandler handler)"]
    BR["方法: List<T> listBindings(String base, NameClassPairMapper<T> mapper)"]
    BS["方法: List<T> listBindings(Name base, NameClassPairMapper<T> mapper)"]
    BT["方法: List<String> listBindings(String base)"]
    BU["方法: List<String> listBindings(Name base)"]
    BV["方法: List<T> listBindings(String base, ContextMapper<T> mapper)"]
    BW["方法: List<T> listBindings(Name base, ContextMapper<T> mapper)"]
    BX["方法: T executeReadOnly(ContextExecutor<T> ce)"]
    BY["方法: T executeReadWrite(ContextExecutor<T> ce)"]
    BZ["方法: T executeWithContext(ContextExecutor<T> ce, DirContext ctx)"]
    CA["方法: Object lookup(Name dn)"]
    CB["方法: Object lookup(String dn)"]
    CC["方法: T lookup(Name dn, AttributesMapper<T> mapper)"]
    CD["方法: T lookup(String dn, AttributesMapper<T> mapper)"]
    CE["方法: T lookup(Name dn, ContextMapper<T> mapper)"]
    CF["方法: T lookup(String dn, ContextMapper<T> mapper)"]
    CG["方法: T lookup(Name dn, String[] attributes, AttributesMapper<T> mapper)"]
    CH["方法: T lookup(String dn, String[] attributes, AttributesMapper<T> mapper)"]
    CI["方法: T lookup(Name dn, String[] attributes, ContextMapper<T> mapper)"]
    CJ["方法: T lookup(String dn, String[] attributes, ContextMapper<T> mapper)"]
    CK["方法: void modifyAttributes(Name dn, ModificationItem[] mods)"]
    CL["方法: void modifyAttributes(String dn, ModificationItem[] mods)"]
    CM["方法: void bind(Name dn, Object obj, Attributes attributes)"]
    CN["方法: void bind(String dn, Object obj, Attributes attributes)"]
    CO["方法: void unbind(Name dn)"]
    CP["方法: void unbind(String dn)"]
    CQ["方法: void unbind(Name dn, boolean recursive)"]
    CR["方法: void unbind(String dn, boolean recursive)"]
    CS["方法: void doUnbind(Name dn)"]
    CT["方法: void doUnbind(String dn)"]
    CU["方法: void doUnbindRecursively(Name dn)"]
    CV["方法: void doUnbindRecursively(String dn)"]
    CW["方法: void deleteRecursively(DirContext ctx, Name name)"]
    CX["方法: void rebind(Name dn, Object obj, Attributes attributes)"]
    CY["方法: void rebind(String dn, Object obj, Attributes attributes)"]
    CZ["方法: void rename(Name oldDn, Name newDn)"]
    DA["方法: void rename(String oldDn, String newDn)"]
    DB["方法: void afterPropertiesSet()"]
    DC["方法: void closeContextAndNamingEnumeration(DirContext ctx, NamingEnumeration results)"]
    DD["方法: void closeContext(DirContext ctx)"]
    DE["方法: void closeNamingEnumeration(NamingEnumeration results)"]
    DF["方法: SearchControls getDefaultSearchControls(int searchScope, boolean returningObjFlag, String[] attrs)"]
    DG["方法: void assureReturnObjFlagSet(SearchControls controls)"]
    DH["方法: DirContextOperations lookupContext(Name dn)"]
    DI["方法: DirContextOperations lookupContext(String dn)"]
    DJ["方法: void modifyAttributes(DirContextOperations ctx)"]
    DK["方法: void bind(DirContextOperations ctx)"]
    DL["方法: void rebind(DirContextOperations ctx)"]
    DM["方法: boolean authenticate(Name base, String filter, String password)"]
    DN["方法: boolean authenticate(String base, String filter, String password)"]
    DO["方法: boolean authenticate(String base, String filter, String password, AuthenticatedLdapEntryContextCallback callback)"]
    DP["方法: boolean authenticate(Name base, String filter, String password, AuthenticatedLdapEntryContextCallback callback)"]
    DQ["方法: boolean authenticate(String base, String filter, String password, AuthenticationErrorCallback errorCallback)"]
    DR["方法: boolean authenticate(Name base, String filter, String password, AuthenticationErrorCallback errorCallback)"]
    DS["方法: boolean authenticate(String base, String filter, String password, AuthenticatedLdapEntryContextCallback callback, AuthenticationErrorCallback errorCallback)"]
    DT["方法: boolean authenticate(Name base, String filter, String password, AuthenticatedLdapEntryContextCallback callback, AuthenticationErrorCallback errorCallback)"]
    DU["方法: AuthenticationStatus authenticate(Name base, String filter, String password, SearchControls searchControls, AuthenticatedLdapEntryContextCallback callback, AuthenticationErrorCallback errorCallback)"]
    DV["方法: T authenticate(LdapQuery query, String password, AuthenticatedLdapEntryContextMapper<T> mapper)"]
    DW["方法: void authenticate(LdapQuery query, String password)"]
    DX["方法: T searchForObject(Name base, String filter, ContextMapper<T> mapper)"]
    DY["方法: T searchForObject(String base, String filter, ContextMapper<T> mapper)"]
    DZ["方法: T searchForObject(Name base, String filter, SearchControls searchControls, ContextMapper<T> mapper)"]
    EA["方法: T searchForObject(String base, String filter, SearchControls searchControls, ContextMapper<T> mapper)"]
    EB["方法: void search(LdapQuery query, NameClassPairCallbackHandler callbackHandler)"]
    EC["方法: List<T> search(LdapQuery query, ContextMapper<T> mapper)"]
    ED["方法: SearchControls searchControlsForQuery(LdapQuery query, boolean returnObjFlag)"]
    EE["方法: List<T> search(LdapQuery query, AttributesMapper<T> mapper)"]
    EF["方法: DirContextOperations searchForContext(LdapQuery query)"]
    EG["方法: T searchForObject(LdapQuery query, ContextMapper<T> mapper)"]
    EH["方法: Stream<T> searchForStream(LdapQuery query, AttributesMapper<T> attributesMapper)"]
    EI["方法: Stream<T> searchForStream(LdapQuery query, ContextMapper<T> mapper)"]
    EJ["方法: Stream<T> searchForStream(LdapQuery query, Function<SearchResult, T> mapper)"]
    EK["方法: T findByDn(Name dn, Class<T> clazz)"]
    EL["方法: void create(Object entry)"]
    EM["方法: void update(Object entry)"]
    EN["方法: void delete(Object entry)"]
    EO["方法: List<T> findAll(Name base, SearchControls searchControls, Class<T> clazz)"]
    EP["方法: List<T> findAll(Class<T> clazz)"]
    EQ["方法: List<T> find(Name base, Filter filter, SearchControls searchControls, Class<T> clazz)"]
    ER["方法: List<T> find(LdapQuery query, Class<T> clazz)"]
    ES["方法: T findOne(LdapQuery query, Class<T> clazz)"]
    ET["方法: Stream<T> findForStream(LdapQuery query, Class<T> clazz)"]
    EU["方法: T unchecked(CheckedSupplier<T> supplier)"]
    EV["接口: CheckedSupplier<T>"]
    EW["枚举: AuthenticationStatus"]
    EX["内部类: NullAuthenticatedLdapEntryContextCallback"]
    EY["内部类: NullDirContextProcessor"]
    EZ["内部类: MappingCollectingNameClassPairCallbackHandler<T>"]
    FA["内部类: NullAuthenticationErrorCallback"]
    FB["内部类: ReturningAuthenticatedLdapEntryContext<T>"]

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
    A --> AM
    A --> AN
    A --> AO
    A --> AP
    A --> AQ
    A --> AR
    A --> AS
    A --> AT
    A --> AU
    A --> AV
    A --> AW
    A --> AX
    A --> AY
    A --> AZ
    A --> BA
    A --> BB
    A --> BC
    A --> BD
    A --> BE
    A --> BF
    A --> BG
    A --> BH
    A --> BI
    A --> BJ
    A --> BK
    A --> BL
    A --> BM
    A --> BN
    A --> BO
    A --> BP
    A --> BQ
    A --> BR
    A --> BS
    A --> BT
    A --> BU
    A --> BV
    A --> BW
    A --> BX
    A --> BY
    A --> BZ
    A --> CA
    A --> CB
    A --> CC
    A --> CD
    A --> CE
    A --> CF
    A --> CG
    A --> CH
    A --> CI
    A --> CJ
    A --> CK
    A --> CL
    A --> CM
    A --> CN
    A --> CO
    A --> CP
    A --> CQ
    A --> CR
    A --> CS
    A --> CT
    A --> CU
    A --> CV
    A --> CW
    A --> CX
    A --> CY
    A --> CZ
    A --> DA
    A --> DB
    A --> DC
    A --> DD
    A --> DE
    A --> DF
    A --> DG
    A --> DH
    A --> DI
    A --> DJ
    A --> DK
    A --> DL
    A --> DM
    A --> DN
    A --> DO
    A --> DP
    A --> DQ
    A --> DR
    A --> DS
    A --> DT
    A --> DU
    A --> DV
    A --> DW
    A --> DX
    A --> DY
    A --> DZ
    A --> EA
    A --> EB
    A --> EC
    A --> ED
    A --> EE
    A --> EF
    A --> EG
    A --> EH
    A --> EI
    A --> EJ
    A --> EK
    A --> EL
    A --> EM
    A --> EN
    A --> EO
    A --> EP
    A --> EQ
    A --> ER
    A --> ES
    A --> ET
    A --> EU
    A --> EV
    A --> EW
    A --> EX
    A --> EY
    A --> EZ
    A --> FA
    A --> FB
```

**描述：**  
`LdapTemplate` 是一个用于简化LDAP操作的类，提供了丰富的搜索、绑定、修改等操作。它封装了LDAP的复杂性，提供了多种方法来处理LDAP条目，包括搜索、列表、绑定、解绑、修改属性等。通过`ContextSource`与LDAP服务器进行交互，并支持多种异常处理和回调机制。类中还包含了一些内部类和枚举，用于处理特定的LDAP操作和异常情况。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| defaultSearchScope = SearchControls.SUBTREE_SCOPE | int | 默认搜索范围设置为子树范围。 |
| contextSource | ContextSource | 私有成员变量contextSource，类型为ContextSource。 |
| ignoreNameNotFoundException = false | boolean | 忽略名称未找到异常的布尔变量。 |
| odm = new DefaultObjectDirectoryMapper() | ObjectDirectoryMapper | 初始化默认对象目录映射器实例。 |
| defaultCountLimit = 0 | int | 默认计数限制初始化为0。 |
| ignoreSizeLimitExceededException = true | boolean | 忽略大小限制异常设置为真。 |
| DONT_RETURN_OBJ_FLAG = false | boolean | 私有静态常量DONT_RETURN_OBJ_FLAG值为false。 |
| ignorePartialResultException = false | boolean | 忽略部分结果异常的布尔变量。 |
| defaultTimeLimit = 0 | int | 默认时间限制初始化为0。 |
| ALL_ATTRIBUTES = null | String[] | 声明了一个私有的静态最终字符串数组ALL_ATTRIBUTES，初始值为null。 |
| LOG = LoggerFactory.getLogger(LdapTemplate.class) | Logger | 定义静态最终日志对象LOG，用于LdapTemplate类的日志记录。 |
| RETURN_OBJ_FLAG = true | boolean | 定义了一个私有静态常量RETURN_OBJ_FLAG，值为true。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| setDefaultSearchScope | void | 设置默认搜索范围的方法。 |
| getDefaultTimeLimit | int | 该方法返回默认时间限制值。 |
| setDefaultCountLimit | void | 设置默认计数限制的方法。 |
| getDefaultSearchScope | int | 获取默认搜索范围的方法。 |
| setIgnorePartialResultException | void | 设置忽略部分结果异常的布尔值。 |
| getObjectDirectoryMapper | ObjectDirectoryMapper | 重写方法返回对象目录映射器实例。 |
| setObjectDirectoryMapper | void | 该方法用于设置对象目录映射器。 |
| getDefaultCountLimit | int | 该方法返回默认计数限制值。 |
| isIgnoreNameNotFoundException | boolean | 方法返回是否忽略名称未找到异常。 |
| setIgnoreSizeLimitExceededException | void | 该方法用于设置是否忽略大小限制超出的异常。 |
| getContextSource | ContextSource | 该方法返回当前对象的contextSource属性。 |
| isIgnorePartialResultException | boolean | 该方法返回是否忽略部分结果异常的布尔值。 |
| isIgnoreSizeLimitExceededException | boolean | 该方法返回是否忽略大小限制超出的异常。 |
| search | List<T> | 重写search方法，支持自定义搜索条件和属性映射。 |
| setContextSource | void | 设置上下文源为指定值。 |
| setDefaultTimeLimit | void | 设置默认时间限制的方法。 |
| search | List<T> | 重写search方法，调用带额外参数的同名方法。 |
| search | List<T> | 重写search方法，调用默认搜索范围进行查询。 |
| search | void | 重写search方法，调用带NullDirContextProcessor的search方法。 |
| search | List<T> | 重写search方法，调用默认搜索控制并返回映射结果。 |
| search | List<T> | 重写search方法，调用带所有属性的search方法。 |
| search | List<T> | 重写搜索方法，调用全属性搜索功能。 |
| search | void | 重写search方法，创建SearchExecutor执行搜索，处理回调和处理程序。 |
| list | void | 重写list方法，使用SearchExecutor执行搜索并调用handler处理结果。 |
| listBindings | List<String> | 重写方法，列出基名称的绑定列表。 |
| search | void | 重写搜索方法，设置搜索控制并调用搜索功能。 |
| list | List<String> | 重写list方法，调用带映射器的list方法。 |
| search | List<T> | 重写search方法，调用带默认搜索范围的search方法。 |
| search | void | 重写search方法，执行搜索并处理回调。 |
| search | List<T> | 重写search方法，调用带ALL_ATTRIBUTES参数的search方法。 |
| search | void | 重写search方法，调用默认搜索控制参数处理搜索请求。 |
| search | void | 方法执行LDAP搜索，处理结果并捕获异常，最后关闭上下文和枚举器。 |
| executeWithContext | T | 执行上下文操作，处理异常并关闭上下文。 |
| search | List<T> | 重写search方法，调用默认搜索范围进行查询。 |
| search | List<T> | 重写search方法，调用带NullDirContextProcessor参数的search方法。 |
| search | List<T> | 该方法使用过滤器和控件搜索LDAP，并通过映射器返回结果列表。 |
| search | List<T> | 重写search方法，调用默认搜索控件，返回映射结果。 |
| search | List<T> | 重写搜索方法，调用带空处理器参数的搜索方法。 |
| search | void | 重写search方法，调用默认搜索控制并处理结果。 |
| search | List<T> | 该方法根据条件搜索并返回映射后的对象列表。 |
| doUnbindRecursively | void | 递归解绑指定名称的LDAP条目。 |
| listBindings | List<T> | 重写方法，使用映射器处理绑定列表并返回结果。 |
| list | List<T> | 重写方法，使用映射器处理列表并返回结果。 |
| lookup | T | 重写lookup方法，根据DN和属性查找并映射上下文。 |
| executeReadWrite | T | 重写executeReadWrite方法，获取读写上下文并执行操作。 |
| bind | void | 重写bind方法，使用上下文执行绑定操作。 |
| search | void | 重写搜索方法，设置默认搜索控制并处理回调。 |
| search | void | 该方法执行LDAP搜索，使用SearchExecutor处理搜索请求，并确保返回对象标志设置。 |
| doUnbind | void | 该方法执行读写操作，解除指定名称的绑定。 |
| doUnbindRecursively | void | 递归解绑指定DN的LDAP条目并执行读写操作。 |
| unbind | void | 该方法用于解绑指定名称的目录条目。 |
| executeReadOnly | T | 重写executeReadOnly方法，获取只读上下文并执行。 |
| lookup | T | 重写方法，通过上下文查找属性并映射返回结果。 |
| modifyAttributes | void | 重写方法，通过上下文执行器修改LDAP属性。 |
| lookup | T | 根据DN和属性查找对象并映射返回。 |
| search | void | 方法search执行搜索，使用SearchExecutor处理搜索请求，并根据handler类型设置controls标志。 |
| lookup | T | 根据DN和属性查找LDAP条目并映射返回结果。 |
| deleteRecursively | void | 递归删除LDAP目录中的条目及其子条目。 |
| list | List<String> | 重写list方法，调用带映射器的list方法。 |
| listBindings | List<T> | 方法listBindings使用ContextMapperCallbackHandler处理绑定并返回列表。 |
| unbind | void | 根据递归参数选择解绑方法。 |
| lookup | Object | 重写lookup方法，通过只读操作执行上下文查找。 |
| search | List<T> | 重写搜索方法，调用默认搜索范围。 |
| listBindings | List<T> | 重写方法，使用ContextMapperCallbackHandler处理绑定列表并返回结果。 |
| afterPropertiesSet | void | 确保contextSource属性设置后执行验证。 |
| modifyAttributes | void | 重写方法用于修改指定DN的属性，执行读写操作并返回null。 |
| search | List<T> | 重写search方法，调用带额外参数的同名方法。 |
| search | List<T> | 重写搜索方法，使用基础、过滤条件、搜索范围、属性和映射器进行查询。 |
| search | List<T> | 重写search方法，设置返回对象标志，使用ContextMapperCallbackHandler处理搜索并返回结果列表。 |
| lookup | T | 方法通过只读操作查找指定DN对象并映射返回结果。 |
| update | void | 更新对象时检查ID变化，若不同则重新绑定，否则修改属性。 |
| rebind | void | 重写rebind方法，执行上下文操作并返回空值。 |
| unbind | void | 该方法用于解绑指定DN，调用doUnbind执行操作。 |
| search | List<T> | 重写搜索方法，支持基名、过滤器、搜索范围和属性映射器参数。 |
| search | List<T> | 重写搜索方法，使用属性映射回调处理器返回结果列表。 |
| lookup | Object | 重写lookup方法，执行只读操作，通过上下文查找指定DN。 |
| list | List<T> | 该方法通过回调处理器映射并返回指定基础路径下的对象列表。 |
| bind | void | bind方法通过上下文绑定对象和属性到指定DN。 |
| unbind | void | unbind方法根据recursive参数选择调用doUnbind或doUnbindRecursively。 |
| listBindings | List<T> | 方法listBindings通过回调处理器获取绑定列表并返回。 |
| rename | void | 重写rename方法，执行上下文重命名操作。 |
| list | void | 重写list方法，使用SearchExecutor执行DirContext的list操作，并调用search方法处理结果。 |
| closeContext | void | 关闭DirContext对象，忽略异常。 |
| listBindings | void | 重写listBindings方法，使用SearchExecutor执行搜索并调用handler处理结果。 |
| lookupContext | DirContextOperations | 重写lookupContext方法，调用lookup并返回DirContextOperations对象。 |
| closeNamingEnumeration | void | 关闭NamingEnumeration资源，忽略异常。 |
| assureReturnObjFlagSet | void | 确保SearchControls的returnObjFlag设置为true。 |
| lookup | T | 重写lookup方法，通过执行只读操作获取属性并映射为指定类型。 |
| closeContextAndNamingEnumeration | void | 关闭上下文和命名枚举，先关闭命名枚举再关闭上下文。 |
| listBindings | void | 重写listBindings方法，使用SearchExecutor执行搜索并调用handler处理结果。 |
| lookup | T | 重写lookup方法，执行只读操作并映射上下文对象。 |
| searchForObject | T | 重写方法，搜索对象并返回映射结果。 |
| rename | void | 重命名方法通过上下文执行器实现目录项更名。 |
| modifyAttributes | void | 重写方法修改DirContextOperations属性，需初始化否则抛出异常。 |
| lookupContext | DirContextOperations | 重写lookupContext方法，调用lookup并返回DirContextOperations对象。 |
| searchControlsForQuery | SearchControls | 根据查询参数配置LDAP搜索控制对象。 |
| getDefaultSearchControls | SearchControls | 获取默认搜索控制参数，设置范围、时间、数量限制及返回属性。 |
| authenticate | boolean | 重写认证方法，调用带回调的认证函数。 |
| bind | void | 重写bind方法，检查DirContextOperations实例初始化状态，未初始化抛出异常。 |
| authenticate | boolean | 重写认证方法，调用带错误回调的认证函数。 |
| search | List<T> | 重写search方法，查询LDAP并返回映射结果列表。 |
| authenticate | boolean | 该方法用于LDAP认证，调用authenticate函数并返回结果。 |
| unchecked | T | 处理LDAP异常，忽略特定异常并记录日志。 |
| authenticate | AuthenticationStatus | LDAP认证方法，验证用户凭据并处理成功或失败回调。 |
| findByDn | T | 根据DN查找LDAP条目并映射为指定类对象。 |
| authenticate | boolean | 重写authenticate方法，调用带回调参数的认证方法。 |
| lookup | T | 重写方法，通过DN查找属性并映射返回结果。 |
| search | void | 重写search方法，根据查询参数和回调处理器执行LDAP搜索。 |
| searchForContext | DirContextOperations | 重写searchForContext方法，查询并返回DirContextOperations对象。 |
| authenticate | boolean | 该方法用于LDAP认证，调用默认搜索控件并返回认证结果。 |
| findOne | T | 查询单个LDAP对象，结果为空或非唯一时抛出异常。 |
| find | List<T> | 重写方法find，根据查询和类类型返回对象列表。 |
| listBindings | List<String> | 重写方法listBindings，调用带映射器的同名方法。 |
| findAll | List<T> | 该方法查找并返回指定类的所有对象列表。 |
| rebind | void | 方法`rebind`检查`DirContextOperations`实例是否初始化，若未初始化则抛出异常。 |
| doUnbind | void | 私有方法doUnbind通过执行读写操作解除指定DN的绑定。 |
| rebind | void | 方法`rebind`通过`ContextExecutor`执行`ctx.rebind`操作，绑定对象到指定DN。 |
| cast | ContextMapper<T> | 私有方法将ContextMapper类型转换为泛型T的上下文映射器。 |
| searchForObject | T | 该方法通过LDAP查询和映射器搜索对象，返回指定类型结果。 |
| delete | void | 删除对象前验证非空，记录日志，获取ID并解绑。 |
| authenticate | boolean | 重写认证方法，支持LDAP基础名称、过滤器、密码及回调功能。 |
| findAll | List<T> | 重写findAll方法，调用find方法查询指定对象列表。 |
| authenticate | void | 重写认证方法，调用带回调的认证函数。 |
| search | List<T> | 重写search方法，执行LDAP查询并映射结果。 |
| find | List<T> | 方法通过LDAP查询并返回指定类的对象列表。 |
| authenticate | boolean | 重写authenticate方法，调用LdapUtils.newLdapName和NullAuthenticatedLdapEntryContextCallback。 |
| searchForStream | Stream<T> | 重写方法，通过LDAP查询和映射器返回流，处理空对象异常。 |
| searchForObject | T | 重写方法搜索对象，无结果或结果不唯一时抛出异常，返回唯一结果。 |
| authenticate | boolean | 重写认证方法，调用内部认证逻辑并传入空回调参数。 |
| searchForStream | Stream<T> | LDAP查询搜索流处理，返回映射结果并确保资源关闭。 |
| searchForObject | T | 重写searchForObject方法，调用LdapUtils.newLdapName处理base参数。 |
| searchForStream | Stream<T> | 重写方法，使用LdapQuery和AttributesMapper生成Stream<T>。 |
| findForStream | Stream<T> | 重写方法，根据查询和类类型构建LDAP流，处理属性和过滤器，映射上下文并返回流。 |
| create | void | 方法`create`验证非空条目，生成ID，映射到LDAP数据，并绑定上下文。 |
| searchForObject | T | 重写方法，通过LDAP搜索对象并返回映射结果。 |
| authenticate | T | LDAP认证方法，处理查询、密码、映射，捕获错误并返回结果。 |
| setIgnoreNameNotFoundException | void | 设置忽略名称未找到异常的状态。 |




