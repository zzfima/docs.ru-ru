---
title: Объекты Principal и Identity
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: c2fadc2d5bb3a787123678a93fa96f8966debbd5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705955"
---
# <a name="principal-and-identity-objects"></a>Объекты Principal и Identity
Управляемый код может обнаружить удостоверение или роль участника с помощью объекта <xref:System.Security.Principal.IPrincipal>, который содержит ссылку на объект <xref:System.Security.Principal.IIdentity>. Может быть полезно сравнить объекты Identity и Principal с привычными понятиями, такими как учетные записи пользователей и групп. В большинстве сетевых сред учетные записи пользователей представляют пользователей или программы, а учетные записи групп — определенные категории пользователей и предоставленные им права. Аналогичным образом, объекты Identity в .NET Framework представляют собой пользователей, а роли — членства и контексты безопасности. В .NET Framework объект Principal инкапсулирует объект Identity и роль. Приложения .NET Framework предоставляют права объекту Principal на основании его идентификатора, но чаще на основании его участия в роли.  
  
## <a name="identity-objects"></a>Объекты Identity  
 Identity — объект инкапсулирует сведения о проверяемом пользователе или сущности. На самом базовом уровне объект Identity содержит имя и тип проверки подлинности. В качестве имени может использоваться имя пользователя или учетной записи Windows, тогда как типом проверки подлинности может быть поддерживаемый протокол входа в систему, например Kerberos V5 или пользовательское значение. .NET Framework определяет объект <xref:System.Security.Principal.GenericIdentity>, который можно использовать для большинства пользовательских сценариев входа в систему, и более специализированный объект <xref:System.Security.Principal.WindowsIdentity>, который можно использовать, если приложение должно полагаться на проверку подлинности Windows. Кроме того, можно определить свой собственный класс Identity, который инкапсулирует особую информацию пользователя.  
  
 Интерфейс <xref:System.Security.Principal.IIdentity> определяет свойства для доступа к имени и типу проверки подлинности, например Kerberos V5 или NTLM. Все классы **Identity** реализуют интерфейс **IIdentity**. Между объектом **Identity** и токеном процесса Windows NT, под которым выполняется текущий поток, необходимой связи нет. Однако, если объектом **Identity** является объект **WindowsIdentity**, предполагается, что Identity представляет токен безопасности Windows NT.  
  
## <a name="principal-objects"></a>Объекты Principal  
 Объект Principal, представляющий контекст безопасности, в котором работает код. Приложения, реализующие безопасность на основе ролей, предоставляют права на основании роли, связанной с объектом Principal. Как и объекты Identity, .NET Framework предоставляет объект <xref:System.Security.Principal.GenericPrincipal> и объект <xref:System.Security.Principal.WindowsPrincipal>. Можно также определить собственные пользовательские классы Principal.  
  
 Интерфейс <xref:System.Security.Principal.IPrincipal> определяет свойство для доступа к связанному объекту **Identity** , а также метод для определения того, является ли пользователь, определяемый объектом **Principal** , членом данной роли. Все классы **Principal** реализуют интерфейс **IPrincipal**, а также любые необходимые дополнительные свойства и методы. Например, среда CLR предоставляет класс **WindowsPrincipal**, который обеспечивает дополнительные функциональные возможности для сопоставления членства в группе Windows NT или Windows 2000 с ролями.  
  
 Объект **Principal** привязан к объекту контекста вызова (<xref:System.Runtime.Remoting.Messaging.CallContext>) в домене приложения (<xref:System.AppDomain>). Контекст вызова по умолчанию всегда создается с каждым новым **AppDomain**, поэтому всегда доступен контекст вызова для принятия объекта **Principal** . При создании нового потока для него также создается объект **CallContext**. Ссылка на объект **Principal** автоматически копируется из создаваемого потока в объект **CallContext** нового потока. Если среда выполнения не может определить, какой объект **Principal** принадлежит создателю потока, она применяет политику по умолчанию для создания объектов **Principal** и **Identity**.  
  
 Настраиваемая политика для домена приложения определяет правила выбора типа объекта **Principal** для связи с новым доменом приложения. Если позволяет политика безопасности, среда выполнения может создать объекты **Principal** и **Identity**, которые отражают токен операционной системы, связанный с текущим потоком выполнения. По умолчанию среда выполнения использует объекты **Principal** и **Identity**, представляющие пользователей, не прошедших проверку подлинности. Среда выполнения не создаст такие объекты **Principal** и **Identity**, пока код не попытается получить к ним доступ.  
  
 Доверенный код, создающий домен приложения, может установить политику домена приложения, которая управляет процессом создания объектов по умолчанию **Principal** и **Identity**. Такая политика домена приложения применяется ко всем выполняемым потокам в данном домене приложения. Неуправляемый доверенный узел по сути имеет возможность задать эту политику, но управляемый код, задающий эту политику, должен иметь <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> для управления политикой домена.  
  
 При передаче объекта **Principal** через домены приложений, но в рамках одного процесса (и, следовательно, на том же компьютере), инфраструктура удаленного взаимодействия копирует ссылку на объект **Principal**, связанный с контекстом вызывающей функции, в вызываемую функцию.  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Создание объекта WindowsPrincipal](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)
- [Практическое руководство. Создание объектов GenericPrincipal и GenericIdentity](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)
- [Замена объекта Principal](../../../docs/standard/security/replacing-a-principal-object.md)
- [Олицетворение и отмена изменений](../../../docs/standard/security/impersonating-and-reverting.md)
- [Безопасность на основе ролей](../../../docs/standard/security/role-based-security.md)
- [Основные понятия безопасности](../../../docs/standard/security/key-security-concepts.md)
