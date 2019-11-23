---
title: Элемент <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834013"
---
# <a name="serviceauthorization-element"></a>\<serviceAuthorization > элемент

Задает параметры авторизации доступа к операциям службы.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<поведения**](behaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**поведение**](behavior-of-servicebehaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceAuthorization >**  

## <a name="syntax"></a>Синтаксис

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Логическое значение, которое определяет, должны ли все операции службы олицетворять вызывающий объект. Значение по умолчанию — `false`.<br /><br /> Если конкретная операция службы олицетворяет вызывающий объект, контекст потока переключается на контекст вызывающего объекта перед выполнением указанной службы.|  
|principalPermissionMode|Определяет участников, используемых для выполнения операций на сервере. В эти значения входят:<br /><br /> — Нет<br />-Усевиндовсграупс<br />-UseAspNetRoles<br />— Пользовательский<br /><br /> Значение по умолчанию - «UseWindowsGroups». Это значение типа <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Дополнительные сведения об использовании этого атрибута см. в разделе [как ограничить доступ с помощью класса PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Строка, указывающая имя поставщика роли, который предоставляет сведения о роли для приложения Windows Communication Foundation (WCF). Значение по умолчанию - пустая строка.|  
|ServiceAuthorizationManagerType|Строка, содержащая имя типа диспетчера авторизации служб. Дополнительные сведения см. в разделе <xref:System.ServiceModel.ServiceAuthorizationManager>.|  

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|  
|-------------|-----------------|  
|authorizationPolicies|Содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова`add`. Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип. Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований. В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](behavior-of-endpointbehaviors.md)|Содержит коллекцию параметров для поведения службы.|  

## <a name="remarks"></a>Примечания

Этот раздел содержит элементы, влияющие на авторизацию, поставщики пользовательских ролей и олицетворение.  
  
Атрибут `principalPermissionMode` указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода. Значение по умолчанию - `UseWindowsGroups`. Оно указывает, что при попытке доступа к ресурсу поиск удостоверения выполняется в таких группах Windows, как «Администраторы» или «Пользователи». Можно также указать `UseAspNetRoles`, чтобы использовать пользовательский поставщик ролей, настроенный в элементе \<System. Web >, как показано в следующем коде:

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
В следующем коде показан `roleProviderName`, используемый с атрибутом `principalPermissionMode`.
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

Подробный пример использования этого элемента конфигурации см. в разделе [авторизация доступа к операциям службы](../../../wcf/samples/authorizing-access-to-service-operations.md) и [политикам авторизации](../../../wcf/samples/authorization-policy.md).
  
## <a name="see-also"></a>См. также:

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Авторизация доступа к операциям службы](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Практическое руководство. Создание пользовательского диспетчера авторизации для службы](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Политика авторизации](../../../wcf/samples/authorization-policy.md)
