---
title: "Конструкторы (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: 064d8f8b3068596cd1d4fc2dd073f165f0ebadcb
ms.contentlocale: ru-ru
ms.lasthandoff: 05/15/2017

---
# <a name="constructors-c-programming-guide"></a>Конструкторы (Руководство по программированию на C#)
Каждый раз, когда создается [класс](../../../csharp/language-reference/keywords/class.md) или [структура](../../../csharp/language-reference/keywords/struct.md), вызывается конструктор. Класс или структура может иметь несколько конструкторов, принимающих различные аргументы. Конструкторы позволяют программисту задавать значения по умолчанию, ограничивать число установок и писать код, который является гибким и удобным для чтения. Дополнительные сведения и примеры см. в разделах [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) и [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="default-constructors"></a>Конструкторы по умолчанию
  
Если не предоставить конструктор для класса, C# создаст конструктор по умолчанию, который создает экземпляр объекта и задаст переменным-членам значения по умолчанию, как показано в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md). Если не предоставить конструктор для структуры, C# будет использовать *неявный конструктор по умолчанию*, чтобы автоматически инициализировать каждое поле типа значения значением по умолчанию, как показано в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md). Дополнительные сведения и примеры см. в разделе [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="constructor-syntax"></a>Синтаксис конструктора

Конструктор — это метод, имя которого совпадает с именем его типа. Его сигнатура метода содержит только имя метода и список параметров. Она не содержит возвращаемый тип. В приведенном ниже примере демонстрируется конструктор для класса с именем `Person`.

[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Если конструктор поддерживает реализацию в виде оператора, можно использовать [определение тела выражения](../statements-expressions-operators/expression-bodied-members.md). В следующем примере определяется класс `Location`, конструктор которого имеет один строковый параметр *name*. Определение тела выражения присваивает аргумент свойству `Name`.

[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Статические конструкторы

В приведенных выше примерах показаны конструкторы экземпляров, которые создают новый объект. В классе или структуре также может быть статический конструктор, который инициализирует статические члены типа.  Статические конструкторы не имеют параметров. Если не предоставить статический конструктор для инициализации статических полей, компилятор C# будет использовать статический конструктор по умолчанию, который инициализирует поля значениями по умолчанию, как указано в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md). 

В следующем примере статический конструктор используется для инициализации статического поля.

[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

Можно также определить статический конструктор с помощью определения тела выражения, как показано в следующем примере. 

[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Дополнительные сведения и примеры см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [Закрытые конструкторы](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [Практическое руководство. Создание конструктора копии](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [Why Do Initializers Run In The Opposite Order As Constructors? Part One](http://go.microsoft.com/fwlink/?LinkId=112374) (Почему инициализаторы выполняются в порядке, обратном действию конструкторов? Часть 1)
