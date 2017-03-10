---
title: "Преобразования указателей (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "указатели [C#], преобразования"
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Преобразования указателей (Руководство по программированию на C#)
В следующей таблице показаны предопределенные неявные преобразования указателей.  Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.  
  
## Неявные преобразования указателей  
  
|Исходный тип|Целевой тип|  
|------------------|-----------------|  
|Любой тип указателя|void\*|  
|null|Любой тип указателя|  
  
 Явное преобразование указателя используется для выполнения преобразований, для которых невозможно неявное преобразование, с помощью выражения приведения.  В следующей таблице приведено описание этих преобразований.  
  
## Явные преобразования указателей  
  
|Исходный тип|Целевой тип|  
|------------------|-----------------|  
|Любой тип указателя|Любой другой тип указателя|  
|sbyte, byte, short, ushort, int, uint, long или ulong|Любой тип указателя|  
|Любой тип указателя|sbyte, byte, short, ushort, int, uint, long или ulong|  
  
## Пример  
 В следующем пример указатель на `int` преобразуется в указатель на `byte`.  Обратите внимание на то, что указатель указывает на наименьший адресуемый байт переменной.  При последовательном увеличении результата до размера `int` \(4 байта\) можно отобразить оставшиеся байты переменной.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#3)]  
  
 [!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#4)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)