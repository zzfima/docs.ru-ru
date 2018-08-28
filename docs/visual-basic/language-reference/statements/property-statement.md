---
title: Property Statement (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 21ca15d6a6939d884c7e6abedc1f7919be079edd
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999529"
---
# <a name="property-statement"></a>Property Statement
Объявляет имя свойства и процедуры свойства, используемые для хранения и извлечения значения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a>Части  
  
-   `attributelist`  
  
     Необязательный. Список атрибутов, применяемых к этому свойству или `Get` или `Set` процедуры. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Необязательный. Указывает, что это свойство является свойством по умолчанию для класса или структуры, в котором она определена. Свойства по умолчанию, должен принимать параметры и их можно задавать и получать без указания имени свойства. При объявлении свойства в виде `Default`, нельзя использовать `Private` в свойстве или любой из его процедур.  
  
-   `accessmodifier`  
  
     Необязательно. на `Property` инструкции и на более одного `Get` и `Set` инструкций. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md) 

    - [Частный защищенный](../../language-reference/modifiers/private-protected.md)
  
     См. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `propertymodifiers`  
  
     Необязательный. Ниже указаны доступные значения.  
  
    -   [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Необязательный. См. в разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Необязательный. См. в разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Необязательный. См. в разделе [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Необязательный. См. в разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Обязательно. Имя свойства. См. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Необязательный. Список имена локальных переменных, представляющих параметры этого свойства и возможные дополнительные параметры `Set` процедуры. См. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Обязателен, если `Option Strict` является `On`. Тип данных значения, возвращаемого этим свойством.  
  
-   `Implements`  
  
     Необязательный. Указывает, что это свойство реализует один или несколько свойств, каждая из которых определена в интерфейс, реализуемый этого свойства классом или структурой. См. в разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых свойств.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |Отделение|Описание:|  
    |---|---|  
    |`interface`|Обязательно. Имя интерфейса, реализуемого этим свойством, содержащей, класс или структура.|  
    |`definedname`|Обязательно. Имя, по которому это свойство определено в `interface`.|  
  
-   `Get`  
  
     Необязательный. Требуется, если свойство помечено `WriteOnly`. Запускает `Get` свойство процедуру, которая используется для возврата значения свойства.  
  
-   `statements`  
  
     Необязательный. Блок операторов для выполнения в рамках `Get` или `Set` процедуры.  
  
-   `End Get`  
  
     Завершает `Get` процедуры свойства.  
  
-   `Set`  
  
     Необязательный. Требуется, если свойство помечено `ReadOnly`. Запускает `Set` свойство процедуру, которая используется для хранения значения свойства.  
  
-   `End Set`  
  
     Завершает `Set` процедуры свойства.  
  
-   `End Property`  
  
     Завершает определение этого свойства.  
  
## <a name="remarks"></a>Примечания  
 `Property` Инструкция содержит объявление свойства. Свойство может иметь `Get` процедура (только для чтения), `Set` процедура (только запись) или оба (чтение и запись). Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Можно использовать `Property` только на уровне класса. Это означает, что *контекст объявления* свойства должен быть класс, структура, модуль или интерфейс, и не может быть исходный файл, пространство имен, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 По умолчанию свойства используют общий доступ. Можно настроить уровень доступа свойства с модификатором доступа на `Property` инструкции и при необходимости можно определить один из его процедур более строгий уровень доступа.  
  
 Visual Basic передает параметр `Set` процедуры во время назначения свойств. Если не указать параметр для `Set`, интегрированную среду разработки (IDE) использует неявный параметр с именем `value`. Этот параметр содержит значение, присваиваемое свойству. Обычно вы сохраните это значение в закрытую локальную переменную и вернуть его каждый раз, когда `Get` при вызове процедуры.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанным уровнем доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого, уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедуры `Private`, но не `Public`.  
  
     При определении `ReadOnly` или `WriteOnly` свойство, одна процедура (`Get` или `Set`, соответственно) представляет все свойства. Нельзя объявлять другой уровень доступа для таких процедур, так как это установит два уровня доступа для свойства.  
  
-   **Тип возвращаемого значения.** `Property` Инструкции можно объявить тип данных значения, он возвращает. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если вы не укажете `returntype`, это свойство возвращает `Object`.  
  
-   **Реализация.** Если это свойство использует `Implements` должен иметь ключевое слово, содержащим классом или структурой `Implements` оператору сразу же после его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, указанного в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Property` (в `definedname`) не обязательно совпадает с именем этого свойства (в `name`).  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры свойства.** Когда `Get` или `Set` процедура возвращает в вызывающий код, выполнение продолжается с оператора, следующего инструкции, вызвавшей его.  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое количество `Exit Property` и `Return` инструкций может находиться в любом в процедуре, и вы можете комбинировать `Exit Property` и `Return` инструкций.  
  
-   **Возвращаемое значение.** Для возвращения значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в `Return` инструкции. В следующем примере присваивается значение имени свойства `quoteForTheDay` , а затем использует `Exit Property` инструкция возвращает.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     Если вы используете `Exit Property` без присвоения значения `name`, `Get` процедура возвращает значение по умолчанию для типа данных свойства.  
  
     `Return` Оператор, в то же время назначает `Get` процедура возвращать значение и завершает процедуру. Это показано в следующем примере.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется свойство в классе.  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Default](../../../visual-basic/language-reference/modifiers/default.md)
