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
ms.openlocfilehash: 9377d889f56049720ab10439582300913f5cbb37
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48263798"
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
|`attributelist`|Необязательный. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Частный защищенный](../../language-reference/modifiers/private-protected.md) <br /><br /> См. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Необязательный. Указывает частичное определение структуры. См. в разделе [частичного](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательно. Имя этой структуры. См. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный. Указывает, что это структурой универсального типа.|  
|`typelist`|Требуется при использовании [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Список параметров типа для этой структуры. См. в разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Необязательный. Указывает, что эта структура реализует члены один или несколько интерфейсов. См. в разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Требуется при использовании `Implements` инструкции. Имена интерфейсов, реализуемых этой структуры.|  
|`datamemberdeclarations`|Обязательно. Ноль или более `Const`, `Dim`, `Enum`, или `Event` объявляющих *данные-члены* структуры.|  
|`methodmemberdeclarations`|Необязательный. Ноль или несколько объявлений `Function`, `Operator`, `Property`, или `Sub` процедуры, которые служат в качестве *метода члены* структуры.|  
|`End Structure`|Обязательно. Завершает `Structure` определения.|  
  
## <a name="remarks"></a>Примечания  
 `Structure` Оператор определяет тип составного значения, которые можно настраивать. Объект *структура* представляет собой обобщение определяемого пользователем типа (UDT) предыдущих версий Visual Basic. Дополнительные сведения см. в разделе [структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Структуры поддерживают многие из те же функции, что классы. Например структуры могут иметь свойства и процедуры, они могут реализовывать интерфейсы и иметь параметризованные конструкторы. Тем не менее существуют значительные различия между структурами и классами в областях, таких как наследование, объявления и использования. Кроме того классы — ссылочными типами и структуры являются типами значений. Дополнительные сведения см. в разделе [структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Можно использовать `Structure` только на уровне пространства имен или модуля. Это означает, что *контекст объявления* структуру должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс, и не может быть процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 По умолчанию структур [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Вложение.** Вы можете определить одну структуру в другую. Внешняя структура называется *содержащего структуру*, и внутренние структуры называются *вложенные структуры*. Тем не менее не может обращаться к членам вложенной структуры через содержащей его структуре. Вместо этого необходимо объявить переменную типа данных вложенной структуры.  
  
-   **Объявление члена.** Необходимо объявить каждый член структуры. Член структуры не может быть [Protected](../../../visual-basic/language-reference/modifiers/protected.md) или `Protected Friend` поскольку ничего не может наследовать из структуры. Структура, тем не менее, может быть `Protected` или `Protected Friend`.  
  
     Можно объявить ноль или более совместно переменные или непользовательским событий в структуре. Не может иметь только константы, свойства и процедуры, даже если некоторые из них не используются совместно.  
  
-   **Инициализация.** Не удается инициализировать значение любого члена совместно данных как часть объявления структуры. Необходимо инициализировать такого члена данных с помощью параметризованного конструктора на структуре или назначить значение элемента, после создания экземпляра структуры.  
  
-   **Наследование.** Структура не может наследовать от любого типа, отличное от <xref:System.ValueType>, от которого наследуют все структуры. В частности одна структура не может наследовать от другого.  
  
     Нельзя использовать [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) в определение структуры, даже для указания <xref:System.ValueType>.  
  
-   **Реализация.** Если используется структура [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), должен реализовывать все члены каждого интерфейса, указываемое в `interfacenames`.  
  
-   **Свойство по умолчанию.** Структуру можно указать не более одного свойства, как его *свойство по умолчанию*, с использованием [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md) модификатор. Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** В структуре можно объявить каждый член со своим собственным уровнем доступа. По умолчанию все члены структуры [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступа. Обратите внимание на то, что если самой структуры имеет больше ограничений, уровень доступа, это автоматически ограничивает доступ к его элементы, даже если изменить уровни доступа с помощью модификаторов доступа.  
  
-   **Область.** Структура — область действия его содержащего пространства имен, класса, структуры или модуля.  
  
     Область действия каждого члена структуры является вся структура.  
  
-   **Время существования.** Структура не сама по себе имеет время существования. Вместо этого каждый экземпляр этой структуры имеет время существования, независимое от всех других экземпляров.  
  
     Время существования экземпляра начинается, когда она была создана программой [оператор New](../../../visual-basic/language-reference/operators/new-operator.md) предложение. Оно заканчивается, когда заканчивается время существования переменной, содержащей его.  
  
     Не удалось увеличить время существования экземпляра структуры. Приближение к функциональным возможностям статическая структура предоставляется в модуле. Дополнительные сведения см. в разделе [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Члены структуры имеют время существования, в зависимости от того, как и где они объявлены. Дополнительные сведения см. в разделе «Время жизни» в [оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Квалификации.** Код вне структуры нужно уточнить имя члена с именем этой структуры.  
  
     Если код внутри вложенной структуры делает неопределенную ссылку на элемент программирования, Visual Basic сначала выполняет поиск элемента в вложенной структуры, затем в его содержащей его структуре, и т. д для внешнего содержащего элемента. Дополнительные сведения см. в разделе [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Потребление памяти.** Как и в случае всех составных типов данных, нельзя вычислить безопасно общее потребление памяти структуры путем сложения распределения Номинальное дисковое его членов. Кроме того нельзя рассчитывать на безопасно порядок элементов в памяти: так же, как порядок их объявления. Если вам нужно управлять макетом структуры хранилища, вы можете применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут `Structure` инструкции.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Structure` инструкцию для определения набора связанных данных о сотруднике. Демонстрирует использование элемента `Public`, `Friend`, и `Private` членов в соответствии с доступом к элементам данных. Здесь также показано члены процедуры, свойства и события.  
  
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
