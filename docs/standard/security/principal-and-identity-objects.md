---
title: "Principal and Identity Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WindowsIdentity objects"
  - "GenericIdentity objects"
  - "GenericPrincipal objects"
  - "identity objects, about identity objects"
  - "security [.NET Framework], identity objects"
  - "principal objects, about principal objects"
  - "security [.NET Framework], principals"
  - "WindowsPrincipal objects"
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Principal and Identity Objects
Управляемый код может получить удостоверение или роль принципала с помощью объекта [Principal](frlrfSystemSecurityPrincipalIPrincipalClassTopic), который содержит ссылку на объект [Identity](frlrfSystemSecurityPrincipalIIdentityClassTopic).  Можно сравнить объект\-участник и объект\-удостоверение с такими привычными понятиями, как учетные записи пользователя и группы.  В большинстве сетевых сред учетные записи пользователей представляют собой людей или программы, тогда как учетные записи групп представляют собой определенные категории пользователей и предоставленные им права.  Подобным образом объекты\-удостоверения в .NET Framework представляют собой пользователей, тогда как роли представляют собой членства и контексты безопасности.  В .NET Framework объекты\-участники инкапсулируют объекты\-удостоверения и роль. Приложения .NET Framework предоставляют права участникам на основании их удостоверений или, в общем случае, на основании их членства в роли.  
  
## Объекты Identity  
 Объект\-удостоверение инкапсулирует информацию о проверяемом пользователе или сущности.  В самом общем случае объект\-удостоверение содержит имя и тип проверки подлинности.  Имя может быть именем пользователя или именем учетной записи Windows, тогда как тип проверки подлинности может быть либо поддерживаемым протоколом начала сеанса, таким как Kerberos V5, либо пользовательским значением.  В .NET Framework определен объект <xref:System.Security.Principal.GenericIdentity>, который может быть использован для пользовательских сценариев входа в систему, и более специализированный объект <xref:System.Security.Principal.WindowsIdentity>, если нужно, чтобы приложение использовало проверку подлинности Windows.  Кроме того, можно определить собственный класс удостоверений, который инкапсулирует определенную пользователем информацию.  
  
 Интерфейс <xref:System.Security.Principal.IIdentity> определяет свойства доступа к имени и тип проверки подлинности, например Kerberos V5 или NTLM.  Классы **Identity** реализуют интерфейс **IIdentity**.  Объект **Identity** не обязательно взаимодействует с лексемой процесса Windows NT, под которой выполняется текущий поток.  Однако если объект **Identity** является объектом **WindowsIdentity**, то предполагается, что удостоверение предоставляет лексему безопасности Windows NT.  
  
## Объекты Principal  
 Объект\-участник представляет контекст безопасности, в котором работает код.  Приложения, реализующие безопасность на основании ролей, предоставляют права на основании роли, связанной с объектом\-участником.  Так же, как и в случае с объектом\-удостоверением, .NET Framework реализует объект <xref:System.Security.Principal.GenericPrincipal> и объект <xref:System.Security.Principal.WindowsPrincipal>.  Кроме того, можно определить собственные классы участников.  
  
 Интерфейс <xref:System.Security.Principal.IPrincipal> определяет свойство доступа к связанному объекту **Identity**, а также метод для определения, является ли определенный объектом **Principal** пользователь членом данной роли.  Все классы **Principal** реализуют интерфейс **IPrincipal** точно так же, как и любые другие необходимые дополнительные свойства и методы.  Например, среда CLR реализует класс **WindowsPrincipal**, который обеспечивает дополнительную функциональность для отображения членства групп в Windows NT или Windows 2000 ролям.  
  
 Объект **Principal** привязан к объекту контекста вызова \(<xref:System.Runtime.Remoting.Messaging.CallContext>\) в рамках домена приложения \(<xref:System.AppDomain>\).  Контекст вызова по умолчанию всегда создается с каждым новым **AppDomain**, так что всегда есть доступный контекст вызова для объекта **Principal**.  Когда создается новый поток, для него создается и объект **CallContext**.  Ссылка для объекта **Principal** автоматически копируется из создаваемого потока в новый контекст **CallContext** потока.  Если среда выполнения не может определить, какой объект **Principal** принадлежит создателю потока, она следует политике по умолчанию для создания объектов **Principal** и **Identity**.  
  
 Настраиваемая политика домена приложения определяет правила решения, какой тип объекта **Principal** связать с новым доменом приложения.  Когда политика безопасности это позволяет, среда выполнения может создать объекты **Principal** и **Identity**, которые отражают лексему операционной системы, связанную с текущим потоком выполнения.  По умолчанию среда выполнения использует объекты **Principal** и **Identity**, которые представляют собой пользователей, не прошедших проверку подлинности.  Среда выполнения не создает эти объекты по умолчанию **Principal** и **Identity** до тех пор, пока программный код не попытается получить к ним доступ.  
  
 Доверенный код, создавший домен приложения, может установить политику домена приложения, которая контролирует построение объектов по умолчанию **Principal** и **Identity**.  Эта политика приложения для определенного домена применяется ко всем выполняемым потокам в данном домене приложения.  Неуправляемый доверенный хост имеет возможность устанавливать эту политику, в то время как управляемый код, который устанавливает политику, должен иметь <xref:System.Security.Permissions.SecurityPermission?displayProperty=fullName> для управления политикой домена.  
  
 Когда объект **Principal** передается между доменами приложений, но в рамках одного процесса \(и, следовательно, на этом же компьютере\), инфраструктура удаленного взаимодействия копирует ссылку на объект **Principal**, связанный с контекстом вызывающего объекта, в контекст вызываемого объекта.  
  
## См. также  
 [How to: Create a WindowsPrincipal Object](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)   
 [How to: Create GenericPrincipal and GenericIdentity Objects](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)   
 [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md)   
 [Impersonating and Reverting](../../../docs/standard/security/impersonating-and-reverting.md)   
 [Role\-Based Security](../../../docs/standard/security/role-based-security.md)   
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)