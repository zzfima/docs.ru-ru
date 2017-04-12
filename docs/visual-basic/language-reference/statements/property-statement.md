---
title: "Оператор Property | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87cb32c12ab3238508a6a4bb114306909e409dda
ms.lasthandoff: 03/13/2017

---
# <a name="property-statement"></a>Property Statement
Объявляет имя свойства и процедуры свойства, используемые для хранения и извлечения значения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
     Необязательный. Список атрибутов, применяемых к этому свойству или `Get` или `Set` процедуры. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Необязательный. Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой она определена. Свойства по умолчанию, должен принимать параметры и их можно задавать и получать без указания имени свойства. Если объявить свойство как `Default`, нельзя использовать `Private` для свойства или любой из его процедур.  
  
-   `accessmodifier`  
  
     Является необязательным `Property` инструкции и на более одного `Get` и `Set` инструкции. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
     Необязательный. В разделе [общего](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательный. В разделе [тени](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Необязательный. В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Необязательный. В разделе [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Необязательный. В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Обязательный. Имя свойства. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Необязательный. Список имен локальных переменных, представляющих параметры этого свойства и возможные дополнительные параметры `Set` процедуры. В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Обязателен, если `Option``Strict` — `On`. Тип данных значения, возвращаемого этим свойством.  
  
-   `Implements`  
  
     Необязательный. Указывает, что это свойство реализует одно или несколько свойств, каждая из которых определена в интерфейс, реализуемый этого свойства классом или структурой. В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых свойств.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |Отделение|Описание|  
    |---|---|  
    |`interface`|Обязательный. Имя интерфейса, реализуемого этим свойством, содержащей класс или структуру.|  
    |`definedname`|Обязательный. Имя, в котором определено свойство `interface`.|  
  
-   `Get`  
  
     Необязательный. Требуется, если свойство помечено как `WriteOnly`. Запускает `Get` свойство процедуру, которая используется для возврата значения свойства.  
  
-   `statements`  
  
     Необязательный. Блок операторов для выполнения в `Get` или `Set` процедуры.  
  
-   `End Get`  
  
     Завершает `Get` процедуры свойства.  
  
-   `Set`  
  
     Необязательный. Требуется, если свойство помечено как `ReadOnly`. Запускает `Set` свойство процедура, используемая для хранения значения свойства.  
  
-   `End Set`  
  
     Завершает `Set` процедуры свойства.  
  
-   `End Property`  
  
     Завершает определение данного свойства.  
  
## <a name="remarks"></a>Примечания  
 `Property` Инструкция содержит объявление свойства. Свойство может иметь `Get` (только для чтения), процедура `Set` процедура (только запись), или обе (чтение и запись). Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства. Дополнительные сведения см. в разделе [Auto-Implemented свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Можно использовать `Property` только на уровне класса. Это означает *контекст объявления* свойства должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 По умолчанию свойства используют общий доступ. Можно настроить уровень доступа свойства с модификатором доступа на `Property` инструкции и можно при необходимости настроить одну из его процедур на более строгий уровень доступа.  
  
 Visual Basic передает параметр `Set` процедуры во время назначения свойств. Если не указать параметр для `Set`, интегрированную среду разработки (IDE) использует неявный параметр с именем `value`. Этот параметр содержит значение, присваиваемое свойству. Обычно хранить данное значение в закрытой локальной переменной и возвращается при каждом `Get` при вызове процедуры.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанные уровни доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедура `Private`, но не `Public`.  
  
     При определении `ReadOnly` или `WriteOnly` свойство, одна процедура (`Get` или `Set`соответственно) представляет все свойства. Нельзя объявлять другой уровень доступа для такой процедуры, так как это установит два уровня доступа для свойства.  
  
-   **Возвращаемый тип.** `Property` Оператора можно объявлять тип данных, возвращаемых значений. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если вы не укажете `returntype`, это свойство возвращает `Object`.  
  
-   **Реализация.** Если это свойство использует `Implements` должен иметь ключевое слово, содержащего класса или структуры `Implements` инструкции сразу после его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать интерфейсов, указанных в `implementslist`. Тем не менее имя, по которому определяется интерфейс `Property` (в `definedname`) не обязательно совпадает с именем данного свойства (в `name`).  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры свойства.** Когда `Get` или `Set` процедура возвращает вызывающему коду, выполнение продолжается с оператора, следующего инструкцию, которая его вызвала.  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое число `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и можно смешивать `Exit Property` и `Return` инструкции.  
  
-   **Возвращаемое значение.** Для возврата значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в `Return` инструкции. В следующем примере возвращаемое значение присваивается имени свойства `quoteForTheDay` , а затем использует `Exit Property` инструкции.  
  
     [!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements&#28;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     Если вы используете `Exit Property` без присвоения значения `name`, `Get` процедура возвращает значение по умолчанию для типа данных свойства.  
  
     `Return` Оператор, в то же время назначает `Get` процедура возвращает значение и завершает процедуру. Это показано в следующем примере.  
  
     [!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements&#29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется свойство в классе.  
  
 [!code-vb[VbVbalrStatements&#51;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Инструкции SET](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Список параметров](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Default](../../../visual-basic/language-reference/modifiers/default.md)
