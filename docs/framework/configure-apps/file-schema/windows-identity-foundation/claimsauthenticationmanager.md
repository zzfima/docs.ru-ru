---
title: "&lt;claimsAuthenticationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;claimsAuthenticationManager&gt;
Регистрирует диспетчер проверки подлинности на основе утверждений для входных утверждений.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|type|Определяет пользовательский тип, производный от класса <xref:System.Security.Claims.ClaimsAuthenticationManager>.  Дополнительные сведения о том, как указать атрибут `type` см. в разделе [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferencess).|  
  
### Дочерние элементы  
 Если атрибут `type` или если атрибут ссылается на `type` класс <xref:System.Security.Claims.ClaimsAuthenticationManager>, то элемент `<claimsAuthenticationManager>` не имеет дочерних элементов; однако классы, производные от <xref:System.Security.Claims.ClaimsAuthenticationManager> могут указывать на элементы конфигурации дочернего элемента.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры идентификатора уровня обслуживания.|  
  
## Заметки  
 По умолчанию функциональности предоставленную через класс <xref:System.Security.Claims.ClaimsAuthenticationManager> вторит входящим утверждений.  Если атрибут `type` не указан или если атрибут `type` определяет класс <xref:System.Security.Claims.ClaimsAuthenticationManager>, то элемент `<claimsAuthenticationManager>` не имеет дочерних элементов.  Можно указать атрибут `type` чтобы зарегистрировать тип, производный от класса <xref:System.Security.Claims.ClaimsAuthenticationManager> для реализации настраиваемой расширений функциональности.  Производные классы могут поддерживать конфигурацию по дочерним узлам элемента `<claimsAuthenticationManager>` переопределив метод <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> для обработки этих элементов.  Схема, определенная для дочерних элементов до конструктора класса.  
  
 Наборы элементов `<claimsAuthenticationManager>` свойство <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=fullName>.  
  
## Пример  
  
```  
<system.identityModel>  
    <identityConfiguration name=”MyIdentity”>  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```