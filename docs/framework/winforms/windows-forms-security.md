---
title: "Windows Forms Security | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "designer access security"
  - "permissions, Windows Forms"
  - "Windows Forms, security"
  - "security [Windows Forms]"
  - "access control, Windows Forms"
  - "security policy, Windows Forms"
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Windows Forms Security
В Windows Forms поддерживается модель безопасности, основанная на коде \(уровни безопасности устанавливаются для кода вне зависимости от запускающего его пользователя\).  Это новая схема безопасности, дополняющая подходы к обеспечению безопасности, используемые на компьютерах пользователей.  В число этих подходов могут входить политики, определенные в браузере \(например, безопасность на основе зон в Internet Explorer\) или в операционной системе \(например, безопасность Windows NT, основанная на учетных данных\).  
  
## В этом подразделе  
 [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 Краткое описание модели безопасности платформы .NET Framework и основные шаги, необходимые для обеспечения безопасности приложений Windows Forms.  
  
 [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 Описание доступа к файлам и данным в среде с частичным доверием.  
  
 [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 Описание доступа к возможностям печати в среде с частичным доверием.  
  
 [Additional Security Considerations in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 Описание способов работы с окнами с помощью буфера обмена и процедуры вызова неуправляемого кода в среде с частичным доверием.  
  
## Связанные подразделы  
 [NIB: Default Security Policy](http://msdn.microsoft.com/ru-ru/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 Список разрешений по умолчанию, определенных в наборах разрешений Full Trust, Local Intranet и Internet.  
  
 [NIB: General Security Policy Administration](http://msdn.microsoft.com/ru-ru/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 Сведения по администрированию политики безопасности платформы .NET Framework и повышению уровня разрешений.  
  
 [Dangerous Permissions and Policy Administration](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 Обсуждение разрешений .NET Framework, которые потенциально могут привести к нарушению системы безопасности.  
  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)  
 Ссылки на разделы, в которых приведены рекомендации по написанию безопасного кода для .NET Framework.  
  
 [NIB: Requesting Permissions](http://msdn.microsoft.com/ru-ru/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 Обсуждение использования атрибутов, которые во время выполнения позволяют определить необходимость тех или иных разрешений для запуска кода.  
  
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)  
 Ссылки на разделы, посвященные основным аспектам безопасности кода.  
  
 [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md)  
 Обсуждение основ работы с политикой безопасности времени выполнения .NET Framework.  
  
 [NIB: Determining When to Modify Security Policy](http://msdn.microsoft.com/ru-ru/af749b17-e461-409d-84b9-a3d44789db16)  
 Способы определения необходимости изменения политики по умолчанию, определенной для приложений.  
  
 [NIB: Deploying Security Policy](http://msdn.microsoft.com/ru-ru/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 Обсуждение наилучших способов развертывания изменений политики безопасности.