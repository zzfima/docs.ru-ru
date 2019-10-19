---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 466bb5386235917705344d35c5141c8bf779218d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582645"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
В Visual Basic есть два типа типов: ссылочные типы и типы значений. В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно. Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная. В случае с типами значений каждая переменная имеет собственную копию данных, и операции с одной переменной не могут влиять на другую (за исключением [модификатора ByRef в параметрах](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Типы значений  
 Тип данных — это *тип значения* , если он содержит данные в пределах отдельного выделения памяти. К типам значений относятся следующие.  
  
- Все числовые типы данных  
  
- `Boolean`, `Char` и `Date`  
  
- Все структуры, даже если их члены являются ссылочными типами  
  
- Перечисления, так как их базовый тип всегда `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` или `ULong`  
  
 Каждая структура является типом значения, даже если она содержит члены ссылочного типа. По этой причине типы значений, такие как `Char` и `Integer`, реализуются структурами .NET Framework.  
  
 Тип значения можно объявить с помощью зарезервированного ключевого слова, например `Decimal`. Для инициализации типа значения можно также использовать ключевое слово `New`. Это особенно полезно, если тип имеет конструктор, принимающий параметры. Примером этого является конструктор <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, который создает новое значение `Decimal` из предоставляемых частей.  
  
## <a name="reference-types"></a>Ссылочные типы  
 *Ссылочный тип* хранит ссылку на свои данные. К ссылочным типам относятся следующие:  
  
- `String`  
  
- Все массивы, даже если их элементы являются типами значений  
  
- Типы классов, например <xref:System.Windows.Forms.Form>  
  
- Делегаты  
  
 Класс является *ссылочным типом*. Обратите внимание, что каждый массив является ссылочным типом, даже если его члены являются типами значений.  
  
 Поскольку каждый ссылочный тип представляет базовый класс .NET Framework, при его инициализации необходимо использовать ключевое слово [New operator](../../../../visual-basic/language-reference/operators/new-operator.md) . Следующая инструкция инициализирует массив.  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Элементы, не являющиеся типами  
 Следующие элементы программирования не являются типами, так как их нельзя указать в качестве типа данных для объявленного элемента:  
  
- Пространства имен  
  
- Модули  
  
- события  
  
- Свойства и процедуры  
  
- Переменные, константы и поля  
  
## <a name="working-with-the-object-data-type"></a>Работа с типом данных Object  
 Переменной `Object` типа данных можно назначить либо ссылочный тип, либо тип значения. Переменная `Object` всегда содержит ссылку на данные, а не сами данные. Однако если присвоить тип значения переменной `Object`, она ведет себя так, как если бы она содержала собственные данные. Дополнительные сведения см. в разделе [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Определить, действует ли `Object`ая переменная как ссылочный тип или тип значения, можно, передав его методу <xref:Microsoft.VisualBasic.Information.IsReference%2A> в классе <xref:Microsoft.VisualBasic.Information> пространства имен <xref:Microsoft.VisualBasic?displayProperty=nameWithType>. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> возвращает `True`, если содержимое переменной `Object` представляет ссылочный тип.  
  
## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Преобразования типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
