---
title: '&lt;userNameAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: d81bf3441f4999683b9dc9ab956fff517c20e80e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltusernameauthenticationgt"></a>&lt;userNameAuthentication&gt;
Задает учетные данные службы, основанные на имени пользователя и пароле.  
  
 \<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
\<userNameAuthentication >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<userNameAuthentication  
   cacheLogonTokenLifetime="TimeSpan"  
   cacheLogonTokens="Boolean"   
   customUserNamePasswordValidatorType="String"  
   includeWindowsGroups="Boolean"   
   maxCacheLogonTokens="Integer"  
   membershipProviderName="String"  
   userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|Объект <xref:System.TimeSpan>, определяющий максимальный срок кэширования маркера. Значение по умолчанию - 00:15:00.|  
|`cacheLogonTokens`|Логическое значение, которое указывает, кэшируются ли маркеры входа. Значение по умолчанию — `false`.|  
|`customUserNamePasswordValidatorType`|Строка, указывающая тип настраиваемого проверяющего элемента управления для проверки имени пользователя и пароля. Значение по умолчанию - пустая строка.|  
|`includeWindowsGroups`|Логическое значение, указывающее, включаются ли группы Windows в контекст безопасности. Значение по умолчанию — `true`.<br /><br /> Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы. Если нет необходимости устанавливать список групп, которым принадлежит пользователь, установите значение `false`.|  
|`maxCacheLogonTokens`|Целое число, указывающее максимальное количество маркеров входа для кэширования. Значение должно быть больше нуля. Значение по умолчанию — 128.|  
|`membershipProviderName`|Если атрибуту `clientCredentialType` привязки задано значение `username`, имя пользователя сопоставляется с учетными записями Windows. Такое поведение можно переопределить с помощью этого атрибута, который является строкой, содержащей имя значения <xref:System.Web.Security.MembershipProvider>, предоставляющего соответствующий механизм проверки пароля.|  
|`userNamePasswordValidationMode`|Указывает способ проверки пароля. Допустимые значения:<br /><br /> — Windows<br />-MembershipProvider<br />-Custom<br /><br /> По умолчанию используется Windows. Это атрибут типа <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="remarks"></a>Примечания  
 Если ни одна из используемых службой привязок не настроена для проверки подлинности на основании имени пользователя и пароля, атрибуты этого элемента пропускаются. К ним относятся `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` и `userNamePasswordValidationMode`.  
  
 Если ни одна из используемых службой привязок не настроена на использование проверки подлинности Windows для имени и пароля пользователя, параметры, относящиеся к кэшированию маркеров входа, пропускаются. К ним относятся `cacheLogonTokenLifetime`, `cacheLogonTokens` и `maxCacheLogonTokens`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.UserNameServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
