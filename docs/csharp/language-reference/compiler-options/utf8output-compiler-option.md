---
title: "/utf8output (C# Compiler Options) | Microsoft Docs"
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
  - "/utf8output"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "utf8output compiler option [C#]"
  - "/utf8output compiler option [C#]"
  - "-utf8output compiler option [C#]"
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /utf8output (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр **\/utf8output** приводит к выводу сообщений компилятора с использованием кодировки UTF\-8.  
  
## Синтаксис  
  
```  
/utf8output  
```  
  
## Заметки  
 В некоторых многоязыковых конфигурациях выходные данные компилятора могут неправильно отображаться на консоли.  В случае подобной конфигурации следует использовать параметр **\/utf8output** и направлять выходные данные компилятора в файл.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)