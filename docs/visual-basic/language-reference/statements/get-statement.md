---
title: Получить Statement (Visual Basic)
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
ms.openlocfilehash: ade54b2f00c540a1bf4ede311e1631b2c5d7e3ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742397"
---
# <a name="get-statement"></a>Оператор Get
Объявляет `Get` процедуру, которая используется для получения значения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный параметр. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательно. на более одного `Get` и `Set` инструкций в этом свойстве. Ниже указаны доступные значения.<br /><br /> -   [защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Необязательный параметр. Один или несколько операторов, выполняемых при `Get` вызывается процедура свойства.|  
|`End Get`|Обязательный. Завершает определение `Get` процедуры свойства.|  
  
## <a name="remarks"></a>Примечания  
 Каждое свойство должно иметь `Get` процедуры свойства, если свойство помечено `WriteOnly`. `Get` Процедура используется для возврата текущего значения свойства.  
  
 Visual Basic автоматически вызывает свойства `Get` процедуры, когда выражение запрашивает значение свойства.  
  
 Текст объявления свойства могут содержать только свойства `Get` и `Set` процедур между [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Оно не может хранить ничего, кроме этих процедур. В частности он не может сохранить текущее значение свойства. Необходимо сохранить это значение за пределами свойства, так как при сохранении внутри одной из процедур свойства, другая процедура свойства к нему нет доступа. Обычный способ — хранить значение в [частного](../../../visual-basic/language-reference/modifiers/private.md) переменная, объявленная на том же уровне, так как свойство. Необходимо определить `Get` процедуры внутри свойства, к которому он применяется.  
  
 `Get` Процедуры по умолчанию используется уровень доступа свойства, содержащего только при использовании `accessmodifier` в `Get` инструкции.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанным уровнем доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого, уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Get` процедуры `Private`, но не `Public`.  
  
     При определении `ReadOnly` свойства `Get` процедура представляет все свойство. Нельзя объявлять разные права доступа уровня для `Get`, так как это установит два уровня доступа для свойства.  
  
-   **Тип возвращаемого значения.** [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) можно объявить тип данных значения, он возвращает. `Get` Процедура автоматически возвращает этот тип данных. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если `Property` инструкции не указан `returntype`, процедура возвращает `Object`.  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры.** Когда `Get` процедура возвращает в вызывающий код, выполнение продолжается в операторе, который запросил значение свойства.  
  
     `Get` процедуры свойств может возвращать значение с помощью [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) или назначив возвращаемое значение к имени свойства. Дополнительные сведения см. в разделе «Возвращают значение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое количество `Exit Property` и `Return` инструкций может находиться в любом в процедуре, и вы можете комбинировать `Exit Property` и `Return` инструкций.  
  
-   **Возвращаемое значение.** Для возвращения значения из `Get` процедуры, можно присвоить значение имени свойства или включить ее в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md). `Return` Оператор одновременно назначает `Get` процедура возвращать значение и завершает процедуру.  
  
     Если вы используете `Exit Property` без присвоения значения к имени свойства `Get` процедура возвращает значение по умолчанию для типа данных свойства. Дополнительные сведения см. в разделе «Возвращают значение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     В следующем примере показано два способа свойство только для чтения `quoteForTheDay` может возвращать значения, которое содержится в закрытой переменной `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Get` инструкция возвращает значение свойства.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>См. также
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Пошаговое руководство: Определение классов](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
