---
title: Property Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "41"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af4666ecb059f141480be2295055644537819293
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="property-statement"></a>Property Statement
Объявляет имя свойства и процедуры свойств, используемых для хранения и извлечения значения свойства.  
  
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
  
     Необязательно. Список атрибутов, которые применяются к этому свойству или `Get` или `Set` процедуры. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Необязательно. Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой она определена. Свойства по умолчанию, должен принимать параметры и можно задавать и получать без указания имени свойства. Если объявляется свойство как `Default`, нельзя использовать `Private` для свойства или любой из его процедур.  
  
-   `accessmodifier`  
  
     Является необязательным `Property` инструкции и на более одного `Get` и `Set` инструкции. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `propertymodifiers`  
  
     Необязательно. Ниже указаны доступные значения.  
  
    -   [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Необязательно. В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательно. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Необязательно. В разделе [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Необязательно. В разделе [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Необязательно. В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Обязательный. Имя свойства. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Необязательно. Список имен локальных переменных, представляющих параметры этого свойства и возможные дополнительные параметры `Set` процедуры. В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Обязателен, если `Option``Strict` — `On`. Тип данных значения, возвращаемого этим свойством.  
  
-   `Implements`  
  
     Необязательно. Указывает, что это свойство реализует один или несколько свойств, каждая из которых определена в интерфейс, реализуемый это свойство классом или структурой. В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых свойств.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |Отделение|Описание|  
    |---|---|  
    |`interface`|Обязательный. Имя интерфейса, реализуемого этим свойством, содержащего класса или структуры.|  
    |`definedname`|Обязательный. Имя, с помощью которого это свойство определено в `interface`.|  
  
-   `Get`  
  
     Необязательно. Требуется, если свойство помечено как `WriteOnly`. Запускает `Get` свойство процедуру, которая используется для возврата значения свойства.  
  
-   `statements`  
  
     Необязательно. Блок операторов для работы в рамках `Get` или `Set` процедуры.  
  
-   `End Get`  
  
     Завершает `Get` процедуры свойства.  
  
-   `Set`  
  
     Необязательно. Требуется, если свойство помечено как `ReadOnly`. Запускает `Set` свойство процедуру, которая используется для хранения значения свойства.  
  
-   `End Set`  
  
     Завершает `Set` процедуры свойства.  
  
-   `End Property`  
  
     Завершает определение данного свойства.  
  
## <a name="remarks"></a>Примечания  
 `Property` Оператор представляет объявление свойства. Свойство может иметь `Get` (только для чтения), процедура `Set` процедура (только запись) или обе (чтение и запись). Можно опустить `Get` и `Set` процедуры при использовании автоматически реализуемого свойства. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Можно использовать `Property` только на уровне класса. Это означает *контекст объявления* свойство должно быть класс, структура, модуль или интерфейс, оно не может быть исходным файлом, пространство имен, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 По умолчанию свойства используют общий доступ. Можно настроить уровень доступа свойства с модификатором доступа на `Property` инструкции и позволяет настроить один из его процедур более строгий уровень доступа.  
  
 Visual Basic передает параметр `Set` процедуры во время назначения свойств. Если не указать параметр для `Set`, интегрированной среды разработки (IDE) использует неявный параметр с именем `value`. Этот параметр содержит значение, присваиваемое свойству. Обычно сохраните значение в частной локальной переменной и возвращается при каждом `Get` при вызове процедуры.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанные уровни доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедура `Private`, но не `Public`.  
  
     При определении `ReadOnly` или `WriteOnly` свойство, одна процедура (`Get` или `Set`соответственно) представляет все свойство. Нельзя объявлять другой уровень доступа для процедуры, так как это установит два уровня доступа для свойства.  
  
-   **Тип возвращаемого значения.** `Property` Инструкции можно объявить тип данных, возвращаемых значений. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если вы не укажете `returntype`, это свойство возвращает `Object`.  
  
-   **Реализация.** Если это свойство использует `Implements` ключевое слово, содержащего класса или структуры, должен иметь `Implements` инструкции сразу после его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, указанным в `implementslist`. Тем не менее имя, по которому интерфейс определяет `Property` (в `definedname`) не должен совпадать с именем этого свойства (в `name`).  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры свойства.** Когда `Get` или `Set` процедура возвращает в вызывающий код, выполнение продолжается с оператора, следующего инструкции, вызвавшей его.  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое количество `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Property` и `Return` инструкции.  
  
-   **Возвращаемое значение.** Для возврата значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в `Return` инструкции. В следующем примере возвращаемое значение присваивается имя свойства `quoteForTheDay` , а затем использует `Exit Property` для возврата.  
  
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
