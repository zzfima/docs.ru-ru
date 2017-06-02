---
title: "Impersonating and Reverting | Microsoft Docs"
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
  - "WindowsIdentity objects, impersonating"
  - "security [.NET Framework], impersonating Windows accounts"
  - "impersonating Windows accounts"
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Impersonating and Reverting
Иногда может потребоваться получить токен учетной записи Windows NT для олицетворения учетной записи Windows. Например, приложению ASP.NET может требоваться действовать от лица разных пользователей в разное время. Ваше приложение может принять токен, представляющий администратора, из служб IIS, выполнить олицетворение этого пользователя, выполнить операцию и вернуться к предыдущему удостоверению. Далее он может принять токен из служб IIS, который представляет пользователя с меньшим набором прав, выполнить некую операцию и снова вернуться.  
  
 В ситуациях, когда приложение должно олицетворять учетную запись Windows, не подключенную к текущему потоку службами IIS, необходимо получить токен для этой учетной записи и с его помощью активировать эту учетную запись. Это можно сделать, выполнив следующие задачи.  
  
1.  Получите токен учетной записи для конкретного пользователя путем вызова неуправляемого метода **LogonUser**. Этот метод находится не в библиотеке базовых классов .NET Framework, а в неуправляемой библиотеке **advapi32.dll**. Доступ к методам в неуправляемом коде является сложной операцией и выходит за рамки данного обсуждения. Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../docs/framework/interop/index.md). Дополнительные сведения о методе **LogonUser** и библиотеке **advapi32.dll** см. в документации Platform SDK.  
  
2.  Создайте новый экземпляр класса **WindowsIdentity**, передав токен. Следующий код демонстрирует этот вызов, где `hToken` представляет токен Windows.  
  
    ```csharp  
    WindowsIdentity ImpersonatedIdentity = new WindowsIdentity(hToken);  
  
    ```  
  
    ```vb  
    Dim ImpersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3.  Начните олицетворение, создав новый экземпляр класса <xref:System.Security.Principal.WindowsImpersonationContext> и инициализировав его с помощью метода <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=fullName> инициализации класса, как показано в следующем коде.  
  
    ```csharp  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate();  
  
    ```  
  
    ```vb  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate()  
    ```  
  
4.  Если это олицетворение больше не требуется, вызовите метод <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=fullName> для отмены олицетворения, как показано в следующем коде.  
  
    ```csharp  
    MyImpersonation.Undo();  
  
    ```  
  
    ```vb  
    MyImpersonation.Undo()  
    ```  
  
 Если доверенный код уже присоединил объект <xref:System.Security.Principal.WindowsPrincipal> к потоку, можно вызвать метод экземпляра **Impersonate**, который не принимает токен учетной записи. Обратите внимание, что это целесообразно только в том случае, если объект **WindowsPrincipal** в потоке представляет пользователя, отличного от того, под которым выполняется процесс. Например, такая ситуация может возникнуть при использовании ASP.NET с включенной проверкой подлинности Windows и отключенным олицетворением. В этом случае процесс выполняется под учетной записью, настроенной в IIS, тогда как текущий участник представляет пользователя Windows, который обращается к странице.  
  
 Обратите внимание, что ни **Impersonate**, ни **Undo** не изменяет объект **Principal** \(<xref:System.Security.Principal.IPrincipal>\), связанный с текущим контекстом вызова. Говоря точнее, эти методы меняют токен, связанный с текущим процессом операционной системы.  
  
## См. также  
 <xref:System.Security.Principal.WindowsIdentity>   
 <xref:System.Security.Principal.WindowsImpersonationContext>   
 [Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md)   
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)