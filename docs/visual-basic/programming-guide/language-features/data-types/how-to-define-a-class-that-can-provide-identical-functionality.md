---
title: Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: d80623d9e55358d37aa45f11f1525c80a09b91a6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350043"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a>Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic)
Можно определить класс, из которого можно создавать объекты, обеспечивающие одинаковые функциональные возможности для различных типов данных. Для этого укажите в определении один или несколько *параметров типа* . После этого класс может служить шаблоном для объектов, которые используют различные типы данных. Класс, определенный таким образом, называется *универсальным классом*.  
  
 Преимущество определения универсального класса состоит в том, он определяется только один раз, и код может использовать его для создания многих объектов, использующих разнообразные типы данных. Это дает более высокую производительность, чем при определении класса с помощью типа `Object` .  
  
 Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.  
  
### <a name="to-define-a-class-with-a-type-parameter"></a>Определение класса с помощью параметра типа  
  
1. Определите класс обычным способом.  
  
2. Добавьте `(Of` *typeparameter*`)` сразу после имени класса для указания параметра типа.  
  
3. Если имеется более одного параметра типа, создайте разделенный запятыми список, заключенный в круглые скобки. Не следует повторять ключевое слово `Of` .  
  
4. Если код выполняет с параметром типа какие-либо операции, отличные от простого присваивания, следует записать данный параметр типа с условием `As` для добавления одного или нескольких *ограничений*. Ограничение гарантирует, что тип, указанный для данного параметра типа, удовлетворяет определенным требованиям:  
  
    - Поддерживает операции, например `>`, которые выполняются кодом.  
  
    - Поддерживает элементы, например методы, к которым обращается код.  
  
    - Предоставляет конструктор без параметров.  
  
     Если не указаны никакие ограничения, код сможет использовать только операции и элементы, поддерживаемые [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). Дополнительные сведения см. в разделе [Type List](../../../../visual-basic/language-reference/statements/type-list.md).  
  
5. Определите все элементы класса, объявляемые с помощью указанного типа, и объявите их `As` `typeparameter`. Это относится к внутреннему хранилищу, параметрам процедур и возвращаемым значениям.  
  
6. Убедитесь, что код использует только операции и методы, поддерживаемые типом данных, который может быть предоставлен для `itemType`.  
  
     В следующем примере определяется класс, управляющий простым списком. Он хранит список во внутреннем массиве `items`, и использующий код может объявить тип данных элементов списка. A parameterized constructor allows the using code to set the upper bound of `items`, and the parameterless constructor sets this to 9 (for a total of 10 items).  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     Можно объявить один класс из `simpleList` для хранения списка значений `Integer` , другой класс — для хранения списка значений `String` и еще один — для хранения значений `Date` . Кроме типа данных элементов списка, объекты, созданные из всех этих классов, ведут себя одинаково.  
  
     Аргумент типа, который использующий код указывает для `itemType` , может быть встроенным типом, например `Boolean` или `Double`, структурой, перечислением или любым типом класса, включая определяемый приложением.  
  
     Можно протестировать класс `simpleList` с помощью следующего кода.  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>См. также

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Независимость от языка и независимые от языка компоненты](../../../../standard/language-independence-and-language-independent-components.md)
- [Of](../../../../visual-basic/language-reference/statements/of-clause.md)
- [Список типов](../../../../visual-basic/language-reference/statements/type-list.md)
- [Практическое руководство. Использование универсального класса](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
