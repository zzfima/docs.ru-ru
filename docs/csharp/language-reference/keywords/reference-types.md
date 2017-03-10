---
title: "Ссылочные типы (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.referencetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, ссылочные типы"
  - "ссылочные типы [C#]"
  - "типы [C#], ссылочные типы"
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Ссылочные типы (Справочник по C#)
В C\# существуют две разновидности типов: ссылочные типы и типы значений.  В переменных ссылочных типов хранятся ссылки на их данные \(объекты\), а переменные типа значений содержат свои данные непосредственно.  Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.  Каждая переменная типа значения имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую \(за исключением переменных параметров out и ref, см. разделы [ref](../../../csharp/language-reference/keywords/ref.md) и [Модификатор параметров out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)\).  
  
 Для объявления ссылочных типов используются следующие ключевые слова:  
  
-   [class](../../../csharp/language-reference/keywords/class.md)  
  
-   [interface](../../../csharp/language-reference/keywords/interface.md)  
  
-   [delegate](../../../csharp/language-reference/keywords/delegate.md)  
  
 В C\# также предусмотрены следующие встроенные ссылочные типы:  
  
-   [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [object](../../../csharp/language-reference/keywords/object.md)  
  
-   [string](../../../csharp/language-reference/keywords/string.md)  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)