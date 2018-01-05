---
title: "Объекты Principal и Identity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WindowsIdentity objects
- GenericIdentity objects
- GenericPrincipal objects
- identity objects, about identity objects
- security [.NET Framework], identity objects
- principal objects, about principal objects
- security [.NET Framework], principals
- WindowsPrincipal objects
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 02c8b4b9f46f051e42fb2ae85a39b6ff48ad2f1a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="principal-and-identity-objects"></a>Объекты Principal и Identity
Управляемый код может получить удостоверение или роль основного через <xref:System.Security.Principal.IPrincipal> объект, который содержит ссылку на <xref:System.Security.Principal.IIdentity> объекта. Может быть полезно сравнить объекты Identity и Principal с привычными понятиями, такими как учетные записи пользователей и групп. В большинстве сетевых сред учетные записи пользователей представляют пользователей или программы, а учетные записи групп — определенные категории пользователей и предоставленные им права. Аналогичным образом, объекты Identity в .NET Framework представляют собой пользователей, а роли — членства и контексты безопасности. В .NET Framework объект Principal инкапсулирует объект Identity и роль. Приложения .NET Framework предоставляют права объекту Principal на основании его идентификатора, но чаще на основании его участия в роли.  
  
## <a name="identity-objects"></a>Объекты Identity  
 Identity — объект инкапсулирует сведения о проверяемом пользователе или сущности. На самом базовом уровне объект Identity содержит имя и тип проверки подлинности. В качестве имени может использоваться имя пользователя или учетной записи Windows, тогда как типом проверки подлинности может быть поддерживаемый протокол входа в систему, например Kerberos V5 или пользовательское значение. Платформа .NET Framework определяет <xref:System.Security.Principal.GenericIdentity> объекта, который может использоваться для большинства сценариев входа в систему и более специализированные <xref:System.Security.Principal.WindowsIdentity> объект, который может использоваться, если необходимо, чтобы приложение использовало проверку подлинности Windows. Кроме того, можно определить свой собственный класс Identity, который инкапсулирует особую информацию пользователя.  
  
 <xref:System.Security.Principal.IIdentity> Интерфейс определяет свойства для доступа к имя и тип проверки подлинности, такие как Kerberos V5 или NTLM. Все классы **Identity** реализуют интерфейс **IIdentity**. Между объектом **Identity** и токеном процесса Windows NT, под которым выполняется текущий поток, необходимой связи нет. Однако, если объектом **Identity** является объект **WindowsIdentity**, предполагается, что Identity представляет токен безопасности Windows NT.  
  
## <a name="principal-objects"></a>Объекты Principal  
 Объект Principal, представляющий контекст безопасности, в котором работает код. Приложения, реализующие безопасность на основе ролей, предоставляют права на основании роли, связанной с объектом Principal. Как и объекты удостоверений, платформа .NET Framework предоставляет <xref:System.Security.Principal.GenericPrincipal> объекта и <xref:System.Security.Principal.WindowsPrincipal> объекта. Можно также определить собственные пользовательские классы Principal.  
  
 <xref:System.Security.Principal.IPrincipal> Интерфейс определяет свойство для доступа к связанным **удостоверение** так же как и метод для определения, определяется ли пользователь **основной** элементом объекта конкретной роли. Все классы **Principal** реализуют интерфейс **IPrincipal**, а также любые необходимые дополнительные свойства и методы. Например, среда CLR предоставляет класс **WindowsPrincipal**, который обеспечивает дополнительные функциональные возможности для сопоставления членства в группе Windows NT или Windows 2000 с ролями.  
  
 Объект **основной** объект привязан к контексту вызова (<xref:System.Runtime.Remoting.Messaging.CallContext>) объекта в домене приложения (<xref:System.AppDomain>). Контекст вызова по умолчанию всегда создается с каждым новым **AppDomain**, поэтому всегда доступен контекст вызова для принятия объекта **Principal** . При создании нового потока для него также создается объект **CallContext**. Ссылка на объект **Principal** автоматически копируется из создаваемого потока в объект **CallContext** нового потока. Если среда выполнения не может определить, какой объект **Principal** принадлежит создателю потока, она применяет политику по умолчанию для создания объектов **Principal** и **Identity**.  
  
 Настраиваемая политика для домена приложения определяет правила выбора типа объекта **Principal** для связи с новым доменом приложения. Если позволяет политика безопасности, среда выполнения может создать объекты **Principal** и **Identity**, которые отражают токен операционной системы, связанный с текущим потоком выполнения. По умолчанию среда выполнения использует объекты **Principal** и **Identity**, представляющие пользователей, не прошедших проверку подлинности. Среда выполнения не создаст такие объекты **Principal** и **Identity**, пока код не попытается получить к ним доступ.  
  
 Доверенный код, создающий домен приложения, может установить политику домена приложения, которая управляет процессом создания объектов по умолчанию **Principal** и **Identity**. Такая политика домена приложения применяется ко всем выполняемым потокам в данном домене приложения. Неуправляемый доверенный хост имеет возможность устанавливать эту политику, но должен иметь управляемый код, который устанавливает политику <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> для управления политикой домена.  
  
 При передаче объекта **Principal** через домены приложений, но в рамках одного процесса (и, следовательно, на том же компьютере), инфраструктура удаленного взаимодействия копирует ссылку на объект **Principal**, связанный с контекстом вызывающей функции, в вызываемую функцию.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание объекта WindowsPrincipal](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)  
 [Практическое руководство. Создание объектов GenericPrincipal и GenericIdentity](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)  
 [Замена объекта Principal](../../../docs/standard/security/replacing-a-principal-object.md)  
 [Олицетворение и отмена изменений](../../../docs/standard/security/impersonating-and-reverting.md)  
 [Безопасность на основе ролей](../../../docs/standard/security/role-based-security.md)  
 [Основные понятия безопасности](../../../docs/standard/security/key-security-concepts.md)
