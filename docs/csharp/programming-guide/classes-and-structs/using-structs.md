---
title: "Использование структур (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94181c42ce913dc76c9a074e4bcbb8240764c896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-structs-c-programming-guide"></a>Использование структур (Руководство по программированию на C#)
Тип `struct` подходит для представления простых объектов, таких как `Point`, `Rectangle`и `Color`. Хотя point удобно представить в виде [класса](../../../csharp/language-reference/keywords/class.md) с [автоматически реализуемыми свойствами](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), в некоторых сценариях [структура](../../../csharp/language-reference/keywords/struct.md) может оказаться более эффективной. Например, при объявлении массива из 1000 объектов `Point` потребуется выделить дополнительную память для ссылки на каждый объект. В этом случае использование структуры будет более экономичным вариантом. Поскольку [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] содержит объект с именем <xref:System.Drawing.Point>, структура в этом примере называется CoOrds.  
  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 Определение конструктора по умолчанию (без параметров) для структуры является ошибочным. Кроме того, ошибкой будет и инициализация поля экземпляра в основной части структуры. Члены доступного извне структуры можно инициализировать только с помощью конструктора с параметрами, неявный конструктор по умолчанию [инициализатора объекта](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md), или путем доступа к членам по отдельности после объявления структуры. Любые закрытые или иным образом недоступные члены исключительно требуют использования конструкторов.
  
 При создании объекта структуры с помощью [новый](../../../csharp/language-reference/keywords/new.md) оператор, создается и соответствующий конструктор вызывается в соответствии с [сигнатура конструктора](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax). В отличие от классов, создавать структуры можно без оператора `new` . В этом случае вызов конструктора не выполняется, что способствует более эффективному выделению ресурсов. Однако поля остаются незназначенными и объект нельзя использовать до инициализации всех полей. Сюда входят о невозможности получить или задать значения с помощью автоматически реализуемых свойств.
 
 При создании экземпляра объекта структуры с помощью конструктора без параметров, по умолчанию, все члены назначенных согласно их [значения по умолчанию](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).
  
 При записи в конструктор с параметрами для структуры, необходимо явно инициализировать все элементы. в противном случае один или несколько членов остаются незназначенными и структуру использовать нельзя, выдать ошибку компилятора CS0171.  
  
 В отличие от классов, структуры не поддерживают наследование. Структура не может наследовать от другой структуры или класса и не может быть базовой для класса. Однако структуры наследуют от базового класса <xref:System.Object>. Структуры могут реализовывать интерфейсы именно так, как это делают классы.  
  
 Нельзя объявить класс с помощью ключевого слова `struct`. В C# классы и структуры имеют разную семантику. Структура является типом значения, а класс — ссылочным типом. Дополнительные сведения см. в разделе [Типы значений](../../../csharp/language-reference/keywords/value-types.md).  
  
 Если не требуется использовать семантику ссылочного типа, система может более эффективно обрабатывать небольшой класс, объявленный как структура.  
  
## <a name="example-1"></a>Пример 1  
  
### <a name="description"></a>Описание  
 В этом примере показана инициализация `struct` с использованием конструктора по умолчанию и параметризованного конструктора.  
  
### <a name="code"></a>Код  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## <a name="example-2"></a>Пример 2  
  
### <a name="description"></a>Описание  
 В этом примере демонстрируется уникальная возможность структур. Здесь создается объект CoOrds без использования оператора `new` . Если заменить слово `struct` на слово `class`, программа не будет скомпилирована.  
  
### <a name="code"></a>Код  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md)
