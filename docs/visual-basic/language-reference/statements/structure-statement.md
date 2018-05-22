---
title: Оператор Structure
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
ms.openlocfilehash: 6fdc4f1d2fbd40689c76a15a5a35b25522138be6
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="structure-statement"></a>Оператор Structure
Объявляет имя структуры и вводит определение переменных, свойств, событий и процедур, которые в структуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`attributelist`|Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Protected Private](../../language-reference/modifiers/private-protected.md) <br /><br /> В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Необязательный. Указывает частичное определение структуры. В разделе [частичного](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательно. Имя этой структуры. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный. Указывает, что это структурой универсального типа.|  
|`typelist`|Является обязательным, если используется [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Список параметров типа для этой структуры. В разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Необязательный. Указывает, что эта структура реализует члены одного или нескольких интерфейсов. В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Является обязательным, если используется `Implements` инструкции. Имена интерфейсов, реализуемых этой структуры.|  
|`datamemberdeclarations`|Обязательно. Ноль или более `Const`, `Dim`, `Enum`, или `Event` объявляющих *данные-члены* структуры.|  
|`methodmemberdeclarations`|Необязательный. Ноль или несколько объявлений `Function`, `Operator`, `Property`, или `Sub` процедур, которые служат в качестве *метода члены* структуры.|  
|`End Structure`|Обязательно. Завершает `Structure` определения.|  
  
## <a name="remarks"></a>Примечания  
 `Structure` Оператор определяет тип составного значения, которые можно настроить. Объект *структура* представляет собой обобщение определяемых пользователем типов (UDT) предыдущих версий Visual Basic. Дополнительные сведения см. в разделе [структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Структуры поддерживают многие из тех же функций, как классы. Например структуры могут иметь свойства и процедуры, они могут реализовывать интерфейсы и иметь параметризованные конструкторы. Однако существуют важные различия между структурами и классами в областях, таких как наследование, объявления и использования. Кроме того классы — ссылочными типами и структуры являются типами значений. Дополнительные сведения см. в разделе [структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Можно использовать `Structure` только на уровне пространства имен или модуля. Это означает *контекст объявления* для структуры должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс и не может быть процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 По умолчанию структуры [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Вложение.** Можно определить одну структуру внутри другой. Внешняя структура называется *содержащего структуру*, и внутренние структуры называются *вложенные структуры*. Тем не менее не может обращаться к членам вложенной структуры через содержащую структуру. Вместо этого необходимо объявить переменную типа данных вложенной структуры.  
  
-   **Объявление члена.** Необходимо объявить каждый член структуры. Член структуры не может быть [Protected](../../../visual-basic/language-reference/modifiers/protected.md) или `Protected Friend` , так как ничего не может наследовать из структуры. Структура, тем не менее, может быть `Protected` или `Protected Friend`.  
  
     Можно объявить ноль или более совместно переменные или непользовательским событий в структуре. Не может иметь только константы, свойства и процедуры, даже если некоторые из них не используются совместно.  
  
-   **Инициализация.** Не удалось инициализировать значение какого-либо совместно данных члена структуры в рамках его объявления. Необходимо инициализировать член данных с помощью конструктора с параметрами в структуре или присвоить значение члену после создания экземпляра структуры.  
  
-   **Наследование.** Структура не может наследовать от любого типа, отличного от <xref:System.ValueType>, от которого наследуют все структуры. В частности одна структура не может наследовать от другого.  
  
     Нельзя использовать [инструкцию наследует](../../../visual-basic/language-reference/statements/inherits-statement.md) в определение структуры, даже для указания <xref:System.ValueType>.  
  
-   **Реализация.** Если используется структура [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), должен реализовывать все члены каждого интерфейса, укажите в `interfacenames`.  
  
-   **Свойство по умолчанию.** Структуру можно указать только одно свойство в качестве его *свойство по умолчанию*, с использованием [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) модификатор. Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** В структуре можно объявить каждый член со своим собственным уровнем доступа. По умолчанию все члены структуры [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа. Обратите внимание, что если самой структуры имеет более ограниченный уровень доступа, это автоматически ограничивает доступ к ее членам, даже если отрегулировать их уровни доступа с помощью модификаторов доступа.  
  
-   **Область действия.** Структура — область действия его содержащего пространства имен, класса, структуры или модуля.  
  
     Область каждого члена структуры является вся структура.  
  
-   **Время существования.** Структура самого имеет время существования. Вместо этого каждый экземпляр данной структуры имеет время существования, независимое от всех других экземпляров.  
  
     Время существования экземпляра начинается, когда она была создана программой [оператор New](../../../visual-basic/language-reference/operators/new-operator.md) предложения. Оно заканчивается, когда время существования переменной, содержащей ее завершении.  
  
     Не удалось увеличить время существования экземпляра структуры. Приближение к функциональности статической структуры обеспечивается модуля. Дополнительные сведения см. в разделе [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Члены структуры имеют время существования в зависимости от того, как и где они объявлены. Дополнительные сведения см. в разделе «Lifetime» в [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Квалификация.** Код вне структуры необходимо предварять именем члена с именем этой структуры.  
  
     Если код внутри вложенной структуры делает неопределенную ссылку на элемент программирования, Visual Basic ищет элемент сначала во вложенной структуре, затем в его содержащей структуре, и т. д для внешнего содержащего элемента. Дополнительные сведения см. в разделе [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Потребление памяти.** Как и все составные типы данных, нельзя вычислить безопасно общее потребление памяти структуры путем сложения выделения Номинальное дисковое его члены. Более того нельзя безошибочно полагать, что порядок расположения элементов в памяти является таким же, как и порядок их объявления. Если вам необходимо управлять структуры хранилища структуры, можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут `Structure` инструкции.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Structure` инструкции для определения набора связанных данных о сотруднике. Показано, как использовать `Public`, `Friend`, и `Private` элементы в соответствии с доступом к элементам данных. Он также содержит члены процедуры, свойства и события.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
