---
title: "/preferreduilang (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
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
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /preferreduilang (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

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