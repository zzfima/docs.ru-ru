---
title: Оператор Structure (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: cec04880dd7cadc627ab090a45468dbad83c8d84
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583210"
---
# <a name="structure-statement"></a>Оператор Structure
Объявляет имя структуры и вводит определение переменных, свойств, событий и процедур, из которых состоит структура.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />[защищенный](../../../visual-basic/language-reference/modifiers/protected.md) -   <br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />- [защищенный дружественный](../../language-reference/modifiers/protected-friend.md)<br/>- [частный защищенный](../../language-reference/modifiers/private-protected.md) <br /><br /> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Необязательный. Указывает на частичное определение структуры. См. раздел [partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательный. Имя этой структуры. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный. Указывает, что это универсальная структура.|  
|`typelist`|Требуется, если используется ключевое слово [of](../../../visual-basic/language-reference/statements/of-clause.md) . Список параметров типа для этой структуры. См. [список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Необязательный. Указывает, что эта структура реализует члены одного или нескольких интерфейсов. См. [инструкцию Implements](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Требуется, если используется оператор `Implements`. Имена интерфейсов, реализуемых этой структурой.|  
|`datamemberdeclarations`|Обязательный. Ноль или более `Const`, `Dim`, `Enum` или `Event` операторы, объявляющие *элементы данных* структуры.|  
|`methodmemberdeclarations`|Необязательный. Ноль или более объявлений `Function`, `Operator`, `Property` или `Sub` процедур, которые служат *членами метода* структуры.|  
|`End Structure`|Обязательный. Завершает определение `Structure`.|  
  
## <a name="remarks"></a>Заметки  
 Оператор `Structure` определяет составной тип значения, который можно настроить. *Структура* представляет собой обобщение определяемого пользователем типа (UDT) предыдущих версий Visual Basic. Дополнительные сведения см. в разделе [структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Структуры поддерживают многие из тех же функций, что и классы. Например, структуры могут иметь свойства и процедуры, они могут реализовывать интерфейсы и могут иметь параметризованные конструкторы. Однако существуют значительные различия между структурами и классами в таких областях, как наследование, объявления и использование. Кроме того, классы являются ссылочными типами, а структуры — типами значений. Дополнительные сведения см. в разделе [структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 @No__t_0 можно использовать только на уровне пространства имен или модуля. Это означает, что *контекст объявления* для структуры должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом и не может быть процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Структуры по умолчанию имеют доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md) . Уровни доступа можно изменить с помощью модификаторов доступа. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
- **Вложенности.** Можно определить одну структуру в другой. Внешняя структура называется *содержащей структурой*, а внутренняя структура называется *вложенной структурой*. Однако нельзя получить доступ к членам вложенной структуры через содержащую их структуру. Вместо этого необходимо объявить переменную типа данных вложенной структуры.  
  
- **Объявление члена.** Необходимо объявить каждый член структуры. Член структуры не может быть [защищен](../../../visual-basic/language-reference/modifiers/protected.md) или `Protected Friend`, так как ничего не может наследовать от структуры. Однако сама структура может быть `Protected` или `Protected Friend`.  
  
     В структуре можно объявить ноль или несколько необщих переменных или нестандартных событий. Нельзя использовать только константы, свойства и процедуры, даже если некоторые из них не являются общими.  
  
- **Инициализации.** Нельзя инициализировать значение несовместного элемента данных структуры как часть его объявления. Необходимо либо инициализировать такой элемент данных с помощью параметризованного конструктора структуры, либо присвоить значение элементу после создания экземпляра структуры.  
  
- **Наследование.** Структура не может наследовать от любого типа, кроме <xref:System.ValueType>, от которого наследуются все структуры. В частности, одна структура не может наследовать от другой.  
  
     Нельзя использовать [инструкцию Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении структуры даже для указания <xref:System.ValueType>.  
  
- **Реализации.** Если в структуре используется [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), необходимо реализовать каждый элемент, определенный каждым интерфейсом, указанным в `interfacenames`.  
  
- **Свойство по умолчанию.** В структуре можно указать не более одного свойства в качестве *свойства по умолчанию*с помощью модификатора [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) . Дополнительные сведения см. в разделе [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** В структуре можно объявить каждый элемент с собственным уровнем доступа. Все члены структуры по умолчанию имеют [Общий](../../../visual-basic/language-reference/modifiers/public.md) доступ. Обратите внимание, что если структура имеет более ограниченный уровень доступа, это автоматически ограничивает доступ к его членам, даже если изменить уровни доступа с помощью модификаторов доступа.  
  
- **Которых.** Структура находится в области, содержащей пространство имен, класс, структуру или модуль.  
  
     Областью видимости каждого члена структуры является вся структура.  
  
- **Контролиру.** Структура сама по себе не имеет времени существования. Вместо этого каждый экземпляр этой структуры имеет время существования, не зависящее от всех других экземпляров.  
  
     Время существования экземпляра начинается, когда оно создается новым предложением [оператора](../../../visual-basic/language-reference/operators/new-operator.md) . Он завершается, когда заканчивается время существования переменной, содержащей ее.  
  
     Нельзя продлить время существования экземпляра структуры. Приближение к функциональности статической структуры обеспечивается модулем. Дополнительные сведения см. в разделе [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Элементы структуры имеют время существования в зависимости от того, как и где они объявляются. Дополнительные сведения см. в разделе "время существования" в [операторе Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
- **Квалификацию.** Код за пределами структуры должен квалифицировать имя члена с именем этой структуры.  
  
     Если код внутри вложенной структуры делает неквалифицированную ссылку на программный элемент, Visual Basic ищет элемент сначала во вложенной структуре, затем в его содержащей его структуре и так далее в самом внешнем содержащем элементе. Для получения дополнительной информации см. [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
- **Потребление памяти.** Как и для всех составных типов данных, вы не можете безопасно вычислить общее потребление памяти для структуры, добавив в них номинальные объемы выделяемого пространства для его членов. Кроме того, нельзя безопасно предположить, что порядок хранения в памяти совпадает с порядком объявления. Если необходимо управлять структурой хранилища структуры, можно применить атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> к инструкции `Structure`.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Structure` используется для определения набора связанных данных для сотрудника. В нем показано использование `Public`, `Friend` и `Private` элементов для отражения чувствительности элементов данных. В нем также показаны члены процедуры, свойства и события.  
  
 [!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>См. также

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
