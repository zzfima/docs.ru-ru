---
title: Список типов (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605294"
---
# <a name="type-list-visual-basic"></a>Список типов (Visual Basic)
Указывает *параметры типа* для *универсального* программный элемент. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`genericmodifier`|Необязательный. Можно использовать только в универсальных интерфейсах и делегатах. Можно объявить тип ковариантного с помощью [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) ключевое слово или контравариантные с помощью [в](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) ключевое слово. См. раздел [Ковариация и контрвариация](../../programming-guide/concepts/covariance-contravariance/index.md).|  
|`typename`|Обязательно. Имя параметра типа. Это заполнитель, должен быть заменен на определенный тип, предоставляемый соответствующий аргумент типа.|  
|`constraintlist`|Необязательный. Список требований, ограничивающих тип данных, который может быть задан для `typename`. Если имеется несколько ограничений, заключайте их в фигурных скобках (`{ }`) и разделяйте их запятыми. Необходимо ввести список ограничений с [как](../../../visual-basic/language-reference/statements/as-clause.md) ключевое слово. Вы используете `As` только один раз в начале списка.|  
  
## <a name="remarks"></a>Примечания  
 Каждый стандартный программный элемент должен принимать хотя бы один параметр типа. Параметр типа является заполнителем для определенного типа ( *построенному элементу*), в коде клиента указывается при создании экземпляра универсального типа. Можно определить универсальный класс, структура, интерфейс, процедуру или делегат.  
  
 Дополнительные сведения о том, когда для определения универсального типа см. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Дополнительные сведения о имена параметров типов. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Правила  
  
-   **Круглые скобки.** Если указать список параметров типа, его следует заключать в круглые скобки и необходимо ввести список с [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Вы используете `Of` только один раз в начале списка.  
  
-   **Ограничения.** Список *ограничения* для типа параметра могут включать следующие элементы в любой комбинации:  
  
    -   Любое число интерфейсов. Указанный тип должен реализовывать каждый интерфейс в этом списке.  
  
    -   Не более одного класса. Указанный тип должен наследовать от этого класса.  
  
    -   Ключевое слово `New`. Данный тип должен предоставлять конструктор без параметров, можно получить доступ к вашей универсального типа. Это полезно, если ограничение параметра типа, один или несколько интерфейсов. Тип, который реализует интерфейсы, необязательно должен предоставлять конструктор, и в зависимости от уровня доступа конструктора, код внутри универсального типа не может быть возможность доступа к ним.  
  
    -   Либо `Class` ключевое слово или `Structure` ключевое слово. `Class` Ключевое слово ограничивает параметр универсального типа для требуют любой тип аргумента, переданного ему был ссылочным типом, например строку, массив или делегат, или объект, созданный из класса. `Structure` Ключевое слово ограничивает параметр универсального типа для требуется, чтобы любой передаваемый ему аргумент типа был типом значения, например тип структуры, перечисления или простейших данных. Нельзя включать оба `Class` и `Structure` в том же `constraintlist`.  
  
     Указанный тип должен удовлетворять каждому требованию, включить в `constraintlist`.  
  
     Ограничения для каждого параметра типа, не зависят от ограничений для других параметров типа.  
  
## <a name="behavior"></a>Поведение  
  
-   **Подстановка времени компиляции.** При создании сконструированного типа из универсального элемента программирования указывается определенного типа для каждого параметра типа. Компилятор Visual Basic подставляет данный предоставленный тип для каждого вхождения `typename` в стандартном элементе.  
  
-   **Отсутствие ограничений.** Если не указаны никакие ограничения, для параметра типа, код ограничивается операции и элементы, поддерживаемые [тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md) для этого параметра типа.  
  
## <a name="example"></a>Пример  
 В следующем примере показано каркасное определение класса универсального словаря, включая каркас функции для добавления новой записи в словарь.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a>Пример  
 Поскольку `dictionary` является универсальным, код, который его использует можно создать различные объекты из него, каждой необходимости те же функциональные возможности, но выполняется для другого типа данных. В следующем примере показано строку кода, который создает `dictionary` объекта с `String` записей и `Integer` ключей.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере каркас определения, созданный в предыдущем примере.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Ковариация и контрвариантность](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
