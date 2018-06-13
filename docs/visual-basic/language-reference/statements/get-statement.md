---
title: Оператор Get
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: d6a6fdfd191de76871619dea3bd1794b487698aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605112"
---
# <a name="get-statement"></a>Оператор Get
Объявляет `Get` процедуру, которая используется для извлечения значения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный на более одного `Get` и `Set` инструкции в этом свойстве. Ниже указаны доступные значения.<br /><br /> -   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Необязательный. Один или несколько операторов, выполняемых при `Get` вызывается процедура свойства.|  
|`End Get`|Обязательно. Завершает определение `Get` процедуры свойства.|  
  
## <a name="remarks"></a>Примечания  
 Каждое свойство должно иметь `Get` процедуры свойства, если свойство помечено как `WriteOnly`. `Get` Процедура используется для возврата текущего значения свойства.  
  
 Visual Basic автоматически вызывает свойство `Get` процедуры, когда выражение запрашивает значение свойства.  
  
 Тело объявления свойства может содержать только свойства `Get` и `Set` процедур между [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Оно не может хранить ничего, кроме этих процедур. В частности он не может хранить текущее значение свойства. Это значение за пределами свойства, необходимо сохранить, поскольку при сохранении внутри любой из процедур свойства, процедуры свойства не может получить доступ к его. Обычный способ — хранить значение в [закрытый](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной в том же уровне, что и свойство. Необходимо определить `Get` процедуры внутри свойства, к которому он применяется.  
  
 `Get` Процедуры по умолчанию устанавливается уровень доступа свойства, содержащего Если вы используете `accessmodifier` в `Get` инструкции.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанные уровни доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Get` процедура `Private`, но не `Public`.  
  
     При определении `ReadOnly` свойства `Get` процедура представляет все свойство. Нельзя объявлять разные права доступа уровня для `Get`, так как это установит два уровня доступа для свойства.  
  
-   **Тип возвращаемого значения.** [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) можно объявить тип данных, возвращаемых значений. `Get` Процедура автоматически возвращает этот тип данных. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если `Property` инструкции не указан `returntype`, процедура возвращает `Object`.  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры.** Когда `Get` процедура возвращает в вызывающий код, выполнение продолжается в операторе, запрошенное значение свойства.  
  
     `Get` процедуры свойств может возвращать значение с помощью [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) , или присвоить возвращаемое значение имени свойства. Дополнительные сведения см. в разделе «Возвращение значения» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое количество `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Property` и `Return` инструкции.  
  
-   **Возвращаемое значение.** Для возврата значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md). `Return` Оператор назначает одновременно `Get` процедура возвращать значение и завершает процедуру.  
  
     Если вы используете `Exit Property` без присвоения значения имени свойства `Get` процедура возвращает значение по умолчанию для типа данных свойства. Дополнительные сведения см. в разделе «Возвращение значения» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     В следующем примере показано два способа только для чтения свойство `quoteForTheDay` может возвращать значение, содержащееся в закрытой переменной `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Get` для возврата значения свойства.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Пошаговое руководство. Определение классов](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
