---
title: "Security and Public Read-only Array Fields | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], public read-only array fields"
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Security and Public Read-only Array Fields
Поля\-массивы с общим доступом только для чтения не следует использовать из управляемых библиотек для определения поведения границ или обеспечения безопасности приложений, поскольку они могут быть изменены.  
  
## Примечания  
 Некоторые классы .NET Framework включают поля с общим доступом только для чтения, содержащие платформо\-зависимые граничные параметры.  Например, поле <xref:System.IO.Path.InvalidPathChars> представляет собой массив, описывающий символы, недопустимые в строке пути к файлу.  В среде .NET Framework имеется немало подобных полей.  
  
 Значения полей с общим доступом только для чтения, таких как <xref:System.IO.Path.InvalidPathChars>, могут быть изменены кодом приложения, или кодом, относящимся к тому же домену приложения.  Подобные поля\-массивы с общим доступом только для чтения не следует использовать для определения граничного поведения приложений.  При нарушении этой рекомендации вредоносный код сможет изменить определения границ и использовать код непредусмотренным образом.  
  
 В .NET Framework версии 2.0 или более поздней следует использовать методы, возвращающие новый массив, вместо использования полей\-массивов с общим доступом.  Например, вместо использования поля <xref:System.IO.Path.InvalidPathChars> следует воспользоваться методом <xref:System.IO.Path.GetInvalidPathChars%2A>.  
  
 Обратите внимание, что типы .NET Framework не используют поля с общим доступом для внутреннего определения граничных типов.  Вместо этого в .NET Framework используются отдельные закрытые поля.  Изменение значений полей с общим доступом не влияет на поведение типов .NET Framework.  
  
## См. также  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)