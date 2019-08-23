---
title: Элемент <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: b73e2049afb460bf9be8b76ee272ba0547b61453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936403"
---
# <a name="serviceauthorization-element"></a>\<Элемент > serviceAuthorization
Задает параметры авторизации доступа к операциям службы.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<serviceAuthorization >  
  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Логическое значение, которое определяет, должны ли все операции службы олицетворять вызывающий объект. Значение по умолчанию — `false`.<br /><br /> Если конкретная операция службы олицетворяет вызывающий объект, контекст потока переключается на контекст вызывающего объекта перед выполнением указанной службы.|  
|principalPermissionMode|Определяет участников, используемых для выполнения операций на сервере. В эти значения входят:<br /><br /> — Нет<br />-Усевиндовсграупс<br />-UseAspNetRoles<br />— Пользовательский<br /><br /> Значение по умолчанию - «UseWindowsGroups». Это значение типа <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Дополнительные сведения об использовании этого атрибута см. в [разделе как Ограничьте доступ с помощью класса](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)PrincipalPermissionAttribute.|  
|roleProviderName|Строка, указывающая имя поставщика роли, который предоставляет сведения о роли для приложения Windows Communication Foundation (WCF). Значение по умолчанию — пустая строка.|  
|ServiceAuthorizationManagerType|Строка, содержащая имя типа диспетчера авторизации служб. Дополнительные сведения см. в разделе <xref:System.ServiceModel.ServiceAuthorizationManager>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|authorizationPolicies|Содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова`add`. Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип. Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований. В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> поведения](behavior-of-endpointbehaviors.md)|Содержит коллекцию параметров для поведения службы.|  
  
## <a name="remarks"></a>Примечания  
 Этот раздел содержит элементы, влияющие на авторизацию, поставщики пользовательских ролей и олицетворение.  
  
 Атрибут `principalPermissionMode` указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода. Значение по умолчанию - `UseWindowsGroups`. Оно указывает, что при попытке доступа к ресурсу поиск удостоверения выполняется в таких группах Windows, как «Администраторы» или «Пользователи». Можно также указать `UseAspNetRoles` , чтобы использовать пользовательский поставщик ролей, настроенный \<в элементе System. Web >, как показано в следующем коде.  
  
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
  
 В следующем примере показано использование элемента `roleProviderName` с атрибутом `principalPermissionMode`.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Авторизация доступа к операциям службы](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Практическое руководство. Создание пользовательского диспетчера авторизации для службы](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Практическое руководство. Ограничение доступа с помощью класса PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Политика авторизации](../../../wcf/samples/authorization-policy.md)
