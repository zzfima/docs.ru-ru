---
title: "Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], байт"
  - "массивы байтов [C#]"
  - "указатели [C#], для копирования байтов"
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Использование указателей для копирования массива байтов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующем примере указатели используются для копирования байт из одного массива в другой.  
  
 В данном примере применяется ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`.  Оператор [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массива.  Это *закрепляет* расположение исходного и конечного массива в памяти, чтобы они не перемещались при сборке мусора.  Закрепление блоков памяти для массивов отменяется, когда завершается обработка блока `fixed`.  Поскольку метод `Copy` в данном примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора **\/unsafe**.  Чтобы задать параметр в Visual Studio, щелкните правой кнопкой мыши имя проекта, затем щелкните **Свойства**.  На вкладке **Построение** выберите команду **Разрешить небезопасный код**.  
  
## Пример  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [\/unsafe \(Enable Unsafe Mode\)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)