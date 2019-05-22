---
title: Руководство по программированию на C#. Использование структур
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 0e0ba1602468d1bcc38985c78e1af5e4d2a5912c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586082"
---
# <a name="using-structs-c-programming-guide"></a>Использование структур (Руководство по программированию на C#)
Тип `struct` подходит для представления простых объектов, таких как `Point`, `Rectangle`и `Color`. Хотя point удобно представить в виде [класса](../../../csharp/language-reference/keywords/class.md) с [автоматически реализуемыми свойствами](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), в некоторых сценариях [структура](../../../csharp/language-reference/keywords/struct.md) может оказаться более эффективной. Например, при объявлении массива из 1000 объектов `Point` потребуется выделить дополнительную память для ссылки на каждый объект. В этом случае использование структуры будет более экономичным вариантом. Поскольку платформа .NET Framework содержит объект с именем <xref:System.Drawing.Point>, структура в этом примере называется "Coords".  
  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 Определение конструктора по умолчанию (без параметров) для структуры является ошибочным. Кроме того, ошибкой будет и инициализация поля экземпляра в основной части структуры. Члены структуры, доступные извне, можно инициализировать только с помощью параметризованного конструктора, неявного конструктора без параметров, [инициализатора объекта](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) или путем доступа к членам по отдельности после объявления структуры. Любые закрытые или недоступные члены требуют исключительного использования конструкторов.
  
 При создании объекта структуры с помощью оператора [new](../../../csharp/language-reference/keywords/new.md) вызывается соответствующий конструктор в соответствии с [сигнатурой конструктора](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax). В отличие от классов, создавать структуры можно без оператора `new` . В этом случае вызов конструктора не выполняется, что способствует более эффективному выделению ресурсов. Однако поля остаются неназначенными и объект нельзя использовать до инициализации всех полей. Например, невозможно получить или задать значения с помощью свойств.
 
 При создании экземпляра объекта структуры с помощью используемого по умолчанию конструктора без параметров все члены назначаются согласно их [значениям по умолчанию](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).
  
 При создании конструктора с параметрами для структуры необходимо явно инициализировать все члены. В противном случае один или несколько членов остаются неназначенными и такую структуру использовать невозможно: это вызывает ошибку компилятора CS0171.  
  
 В отличие от классов, структуры не поддерживают наследование. Структура не может наследовать от другой структуры или класса и не может быть базовой для класса. Однако структуры наследуют от базового класса <xref:System.Object>. Структуры могут реализовывать интерфейсы именно так, как это делают классы.  
  
 Нельзя объявить класс с помощью ключевого слова `struct`. В C# классы и структуры имеют разную семантику. Структура является типом значения, а класс — ссылочным типом. Дополнительные сведения см. в разделе [Типы значений](../../../csharp/language-reference/keywords/value-types.md).  
  
 Если не требуется использовать семантику ссылочного типа, система может более эффективно обрабатывать небольшой класс, объявленный как структура.  
  
## <a name="example-1"></a>Пример 1  
  
### <a name="description"></a>Описание  
 В этом примере показана инициализация `struct` с использованием конструктора по умолчанию и параметризованного конструктора.  
  
### <a name="code"></a>Код  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]  
  
## <a name="example-2"></a>Пример 2  
  
### <a name="description"></a>Описание  
 В этом примере демонстрируется уникальная возможность структур. Здесь создается объект CoOrds без использования оператора `new`. Если заменить слово `struct` на слово `class`, программа не будет скомпилирована.  
  
### <a name="code"></a>Код  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md)
