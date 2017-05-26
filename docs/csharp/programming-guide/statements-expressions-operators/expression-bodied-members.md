---
title: "Члены, воплощающие выражения (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: b77f656d36dc4f0a715755e13bfcd6c3515c697b
ms.contentlocale: ru-ru
ms.lasthandoff: 05/15/2017

---
# <a name="expression-bodied-members-c-programming-guide"></a>Члены, воплощающие выражения (руководство по программированию на C#)
Определения тела выражений позволяют предоставлять реализацию члена самым быстрым и удобочитаемым способом. Определение тела выражения можно использовать, когда логика для любого поддерживаемого члена, такого как метод или свойство, состоит из одного выражения. Определение тела выражения имеет следующий общий синтаксис:

```csharp
member => expression;
```

здесь *expression* является допустимым выражением. 

В C# 6 была представлена поддержка для определений тела выражений для методов и методов доступа Property Get. В C# 7 эта поддержка была расширена. Определения тела выражений можно использовать с членами типа, указанными в следующей таблице. 

|Член  |Поддерживается как... |
|---------|---------|
|[Метод](#methods)  |C# 6 |
|[Конструктор](#constructors)   |C# 7 |
|[Метод завершения](#finalizers)     |C# 7 |
|[Property Get](#property-get-statements)  |C# 6 |
|[Property Set](#property-set-statements)  |C# 7 |
|[Индексатор](#indexers)       |C# 7 |

## <a name="methods"></a>Методы

Метод, воплощающий выражение, состоит из одного выражения, возвращающего значение, тип которого соответствует возвращаемому типу метода, или методов, возвращающих `void`, который выполняет некоторые операции. Например, типы, переопределяющие метод <xref:System.Object.ToString%2A>, обычно содержат одно выражение, которое возвращает строковое представление текущего объекта. 

В следующем примере определяется класс `Person`, который переопределяет метод <xref:System.Object.ToString%2A> с помощью определения тела выражения. Он также определяет метод `Show`, который отображает имя в консоли. Обратите внимание, что ключевое слово `return` не используется в определении тела выражения `ToString`.

[!code-cs[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Дополнительные сведения см. в разделе [Методы (руководство по программированию на C#)](../classes-and-structs/methods.md).
 
## <a name="constructors"></a>Конструкторы

Определение тела выражения для конструктора обычно состоит из одного выражения присваивания или вызова метода, который обрабатывает аргументы конструктора или инициализирует состояние экземпляра. 

В следующем примере определяется класс `Location`, конструктор которого имеет один строковый параметр *name*. Определение тела выражения присваивает аргумент свойству `Name`.

[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Дополнительные сведения см. в разделе [Конструкторы (руководство по программированию на C#)](../classes-and-structs/constructors.md).

## <a name="finalizers"></a>Методы завершения

Определение тела выражения для метода завершения обычно содержит операторы очистки, например операторы, высвобождающие неуправляемые ресурсы.

В следующем примере определяется метод завершения, который использует определение тела выражения для указания того, что был вызван метод завершения.

[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

Дополнительные сведения см. в разделе [Методы завершения (руководство по программированию на C#)](../classes-and-structs/destructors.md).

## <a name="property-get-statements"></a>Операторы Property Get

Если вы решили самостоятельно реализовать метод доступа Property Get, определение тела выражения можно использовать для отдельных выражений, которые просто возвращают значение свойства. Обратите внимание, что оператор `return` не используется.

В следующем примере определяется свойство `Location.Name`, метод доступа Property Get которого возвращает значение закрытого поля `locationName`, поддерживающего свойство. 

[!code-cs[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Свойства только для чтения, использующие определение тела выражения, можно реализовать без явного оператора `set`. Синтаксис выглядит следующим образом.

```csharp
PropertyName => returnValue;
```

В следующем примере определяется класс `Location`, свойство `Name` только для чтения которого реализуется как определение тела выражения, возвращающее значение закрытого поля `locationName`.

[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Дополнительные сведения см. в разделе [Свойства (руководство по программированию на C#)](../classes-and-structs/properties.md).

## <a name="property-set-statements"></a>Операторы Property Set

Если вы решили самостоятельно реализовать метод доступа Property Set, определение тела выражения можно использовать для однострочного выражения, которое присваивает значение полю, поддерживающему свойство.

В следующем примере определяется свойство `Location.Name`, метод доступа Property Set которого присваивает входной аргумент закрытому полю `locationName`, поддерживающему свойство.

[!code-cs[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Дополнительные сведения см. в разделе [Свойства (руководство по программированию на C#)](../classes-and-structs/properties.md).

## <a name="indexers"></a>Индексаторы

Как и свойства, методы доступа set и get индексатора состоят из определений тела выражений, если метод доступа get состоит из одного оператора, который возвращает значение, или метод доступа set выполняет простое присваивание.

В следующем примере определяется класс с именем `Sports`, включающий внутренний массив <xref:System.String>, который содержит названия нескольких видов спорта. Методы доступа get и set индексатора реализуются как определения тела выражений.

[!code-cs[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

Дополнительные сведения см. в разделе [Индексаторы (руководство по программированию на C#)](../indexers/index.md).


