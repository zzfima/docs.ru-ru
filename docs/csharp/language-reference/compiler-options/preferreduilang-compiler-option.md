---
title: "/preferreduilang (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/preferreduilang"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "preferreduilang compiler option [C#]"
  - "/preferreduilang compiler option [C#]"
  - "-preferreduilang compiler option [C#]"
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /preferreduilang (C# Compiler Options)
С помощью параметра компилятора `/preferreduilang` можно указать язык, на котором компилятор C\# отображает выходные данные, такие как сообщения об ошибке.  
  
## Синтаксис  
  
```  
/preferreduilang: language  
```  
  
## Аргументы  
 `language`  
 [Имя языка](http://go.microsoft.com/fwlink/p/?LinkId=236992), который будет использоваться для вывода компилятора.  
  
## Заметки  
 Можно использовать параметр компилятора `/preferreduilang` для указания языка, который требуется от компилятора C\# для сообщений об ошибках и другого вывода командной строки.  Если языковой пакет для требуемого языка не задан, то вместо него используются языковые настройки операционной системы, но ошибка не возникает.  
  
```c#  
csc.exe /preferreduilang:ja-JP  
```  
  
## Требования  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)