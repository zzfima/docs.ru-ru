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
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504879"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
Существуют две разновидности типов в Visual Basic: ссылочные типы и типы значений. В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно. Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная. Типы значений, каждая переменная имеет собственную копию данных, и он не поддерживается для операций над одной переменной могут затрагивать другую (за исключением в случае использования [ByRef модификатор параметров](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Типы значений  
 Тип данных является *тип значения* если он содержит данные в пределах своей собственной памяти. Ниже приведены типы значений:  
  
- Все числовые типы данных  
  
- `Boolean`, `Char`и `Date`  
  
- Все структуры, даже если их элементы являются ссылочными типами  
  
- Перечисления, поскольку их базовый тип всегда является `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, или `ULong`  
  
 Каждая структура является типом значения, даже если он содержит члены ссылочного типа. По этой причине значение типы, такие как `Char` и `Integer` реализуются структуры .NET Framework.  
  
 Можно объявить тип значения с помощью зарезервированного ключевого слова, например, `Decimal`. Можно также использовать `New` ключевое слово для инициализации типа значения. Это особенно полезно в том случае, если тип имеет конструктор, принимающий параметры. Примером этого является <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> конструктор, который создает новый `Decimal` значение из предоставленных частей.  
  
## <a name="reference-types"></a>Ссылочные типы  
 Объект *ссылочный тип* хранит ссылку на его данные. Ссылочные типы включают в себя следующее:  
  
- `String`  
  
- Все массивы, даже в том случае, если их элементы являются типами значений  
  
- Типы классов, такие как <xref:System.Windows.Forms.Form>  
  
- Делегаты  
  
 Класс является *ссылочный тип*. Обратите внимание на то, что каждый массив является ссылочным типом, даже если его члены являются типами значений.  
  
 Так как каждый ссылочный тип представляет собой соответствующий класс .NET Framework, необходимо использовать [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово для его инициализации. Следующая инструкция инициализирует массив.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Элементы, которые не являются типами  
 Следующие элементы программирования не могут считаться типов, так как нельзя указать любой из них как тип данных для объявленного элемента:  
  
- Пространства имен  
  
- Модули  
  
- События  
  
- Свойства и процедуры  
  
- Переменные, константы и поля  
  
## <a name="working-with-the-object-data-type"></a>Работа с типом данных объекта  
 Можно назначить переменной ссылочным типом или типом значения `Object` тип данных. `Object` Переменная не всегда ссылается на данные, а не сами данные. Однако если присвоить тип значения для `Object` переменной, он действует так, будто он хранит собственные данные. Дополнительные сведения см. в разделе [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Вы можете выяснить, был ли `Object` переменная используется в качестве ссылочным типом или типом значения, передав его в <xref:Microsoft.VisualBasic.Information.IsReference%2A> метод в <xref:Microsoft.VisualBasic.Information> класс <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространства имен. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Возвращает `True` Если содержание `Object` переменная представляет ссылочный тип.  
  
## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
