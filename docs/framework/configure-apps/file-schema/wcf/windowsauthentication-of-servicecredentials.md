---
title: "&lt;windowsAuthentication&gt; для &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;windowsAuthentication&gt; для &lt;serviceCredentials&gt;
Задает параметры учетной записи службы Windows.  
  
## Синтаксис  
  
```  
  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`includeWindowsGroups`|Необязательный логический атрибут, который задает, включает ли система группы Windows в контекст безопасности.  Значение по умолчанию — `true`.<br /><br /> Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.  Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.|  
|`allowAnonymousLogons`|Необязательный логический атрибут, который указывает, разрешены ли анонимные, не прошедшие проверку подлинности вызывающие объекты.  Значение по умолчанию — `false`.<br /><br /> Когда атрибуту `clientCredentialType` привязки задано значение `Windows`, система не разрешает анонимные вызывающие объекты.  Это значит, что доступ к системе разрешен только прошедшим проверку подлинности вызывающим объектам домена или рабочей группы.  Это поведение можно переопределить с помощью данного атрибута.<br /><br /> Используйте этот режим с особой осторожностью.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## Заметки  
 Этот элемент используется, чтобы указать, разрешается ли доступ анонимных пользователей Windows путем установки атрибута `allowAnonymousLogons`.  Также можно указать, включать ли сведения о группе, к которой принадлежат пользователи в AuthorizationContext, путем установки атрибута `includeWindowsGroups`.  Если атрибуту задано значение `true` \(по умолчанию\), служба может определить группы Windows, к которым принадлежит клиент.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>   
 <xref:System.ServiceModel.Security.WindowsServiceCredential>