---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152753"
---
# <a name="claimsauthenticationmanager"></a>\<претензииAuthenticationManager>
Регистрирует менеджера проверки подлинности претензий для входящих претензий.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<претензииAuthenticationManager>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|type|Определяет пользовательский тип, который вытекает <xref:System.Security.Claims.ClaimsAuthenticationManager> из класса. Для получения дополнительной информации `type` о том, как указать атрибут, см.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 `type` Если нет атрибута, или `type` если атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> ссылается `<claimsAuthenticationManager>` на класс, элемент не принимает элементы ребенка; однако классы, <xref:System.Security.Claims.ClaimsAuthenticationManager> полученные из элементов конфигурации ребенка, могут определять элементы конфигурации ребенка.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<идентичностьНастройка>](identityconfiguration.md)|Определяет настройки удостоверения уровня обслуживания.|  
  
## <a name="remarks"></a>Remarks  
 Поведение по умолчанию, предоставляемое через класс, <xref:System.Security.Claims.ClaimsAuthenticationManager> перекликается с входящими претензиями. Если `type` атрибут не указан `type` или если атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> определяет класс, `<claimsAuthenticationManager>` элемент не принимает элементы ребенка. Можно указать `type` атрибут для регистрации типа, полученного из <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, для реализации пользовательского поведения. Полученные классы могут поддерживать конфигурацию через элемент детского элемента, `<claimsAuthenticationManager>` переопределяя <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> метод обработки этих элементов. Схема, определенная для элементов ребенка, до дизайнера класса.  
  
 Элемент `<claimsAuthenticationManager>` устанавливает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
