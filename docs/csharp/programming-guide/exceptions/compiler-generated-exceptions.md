---
title: Руководство по программированию на C#. Исключения, создаваемые компилятором
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 2a6b2c3fa053f1c555856df8098975340e78e2b2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705318"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Исключения, создаваемые компилятором (Руководство по программированию в C#)
Некоторые исключения создаются средой .NET Framework CLR (CLR) автоматически, когда происходит сбой основной операции. В следующей таблице перечислены эти исключения и условия возникновения ошибок.  
  
|Исключение|Описание|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Базовый класс для исключений, которые возникают при выполнении арифметических операций, таких как <xref:System.DivideByZeroException> и <xref:System.OverflowException>.|  
|<xref:System.ArrayTypeMismatchException>|Возникает, если массив не может сохранить данный элемент, поскольку фактический тип элемента несовместим с фактическим типом массива.|  
|<xref:System.DivideByZeroException>|Возникает при попытке деления целого значения на ноль.|  
|<xref:System.IndexOutOfRangeException>|Возникает при попытке индексирования массива, если индекс меньше нуля или выходит за границы массива.|  
|<xref:System.InvalidCastException>|Возникает, если явное преобразование из базового типа в интерфейс или в производный тип завершается ошибкой во время выполнения.|  
|<xref:System.NullReferenceException>|Возникает при попытке сослаться на объект, имеющий значение [null](../../language-reference/keywords/null.md).|  
|<xref:System.OutOfMemoryException>|Возникает, если попытка распределения памяти с помощью оператора [new](../../language-reference/operators/new-operator.md) завершается ошибкой. Это означает, что ресурсы памяти, доступные для среды CLR, исчерпаны.|  
|<xref:System.OverflowException>|Возникает при переполнении арифметической операции в контексте `checked`.|  
|<xref:System.StackOverflowException>|Возникает, когда чрезмерное количество ожидающих вызовов метода истощает стек выполнения; обычно это указывает на крайне глубокую или бесконечную рекурсию.|  
|<xref:System.TypeInitializationException>|Возникает, когда статический конструктор создает исключение, а совместимого предложения `catch` для его захвата нет.|  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Исключения и обработка исключений](./index.md)
- [Обработка исключений](./exception-handling.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
