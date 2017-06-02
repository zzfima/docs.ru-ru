---
title: "Элемент &lt;serviceAuthorization&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Элемент &lt;serviceAuthorization&gt;
Задает параметры авторизации доступа к операциям службы.  
  
## Синтаксис  
  
```  
  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|impersonateCallerForAllOperations|Логическое значение, которое определяет, должны ли все операции службы олицетворять вызывающий объект.  Значение по умолчанию — `false`.<br /><br /> Если конкретная операция службы олицетворяет вызывающий объект, контекст потока переключается на контекст вызывающего объекта перед выполнением указанной службы.|  
|principalPermissionMode|Определяет участников, используемых для выполнения операций на сервере.  В эти значения входят:<br /><br /> -   Нет<br />-   UseWindowsGroups<br />-   UseAspNetRoles<br />-   Другой<br /><br /> Значение по умолчанию \- «UseWindowsGroups».  Это значение типа <xref:System.ServiceModel.Description.PrincipalPermissionMode>.  Дополнительные сведения об использовании этого атрибута см. в разделе [Как ограничить доступ с использованием класса PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Строка, указывающая имя поставщика роли, который предоставляет сведения о роли для приложения Windows Communication Foundation \(WCF\).  Значение по умолчанию \- пустая строка.|  
|ServiceAuthorizationManagerType|Строка, содержащая имя типа диспетчера авторизации служб.  Для получения дополнительной информации см. <xref:System.ServiceModel.ServiceAuthorizationManager>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|authorizationPolicies|Содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова`add`.  Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.  Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.  В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.  Для получения дополнительной информации см. <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Содержит коллекцию параметров для поведения службы.|  
  
## Заметки  
 Этот раздел содержит элементы, влияющие на авторизацию, поставщики пользовательских ролей и олицетворение.  
  
 Атрибут `principalPermissionMode` указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода.  Значение по умолчанию \- `UseWindowsGroups`. Оно указывает, что при попытке доступа к ресурсу поиск удостоверения выполняется в таких группах Windows, как «Администраторы» или «Пользователи».  Также можно задать атрибут `UseAspNetRoles` для использования поставщика пользовательской роли, который настроен в элементе \<system.web\>, как показано в приведенном ниже коде.  
  
```  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
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
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 В следующем примере показано использование элемента `roleProviderName` с атрибутом `principalPermissionMode`.  
  
```  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 Подробный пример с иллюстрацией использования данного элемента конфигурации представлен в разделах [Авторизация доступа к операциям службы](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) и [Политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Авторизация доступа к операциям службы](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Как создавать пользовательский диспетчер авторизации для службы](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [Как ограничить доступ с использованием класса PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)   
 [Политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md)