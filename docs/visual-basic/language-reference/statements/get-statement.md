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
ms.openlocfilehash: 9560faf90d531c32f104dbd053a7c1f5584cfb1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351175"
---
# <a name="get-statement"></a>Оператор Get
Объявляет процедуру свойства `Get`, используемую для получения значения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный элемент. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|(Необязательно) не более одного из инструкций `Get` и `Set` в этом свойстве. Ниже указаны доступные значения.<br /><br /> [защищенный](../../../visual-basic/language-reference/modifiers/protected.md) -   <br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Необязательный элемент. Одна или несколько инструкций, выполняемых при вызове процедуры свойства `Get`.|  
|`End Get`|Обязательно. Завершает определение процедуры свойства `Get`.|  
  
## <a name="remarks"></a>Примечания  
 Каждое свойство должно иметь `Get` процедуру свойства, если только свойство не помечено как `WriteOnly`. Процедура `Get` используется для возврата текущего значения свойства.  
  
 Visual Basic автоматически вызывает процедуру `Get` свойства, когда выражение запрашивает значение свойства.  
  
 Тело объявления свойства может содержать только `Get` и `Set` процедуры свойства между [оператором Property](../../../visual-basic/language-reference/statements/property-statement.md) и оператором `End Property`. Он не может хранить ничего, Кроме этих процедур. В частности, он не может хранить текущее значение свойства. Это значение необходимо хранить за пределами свойства, так как при хранении в любой из процедур свойств другая процедура свойства не может получить к ней доступ. Обычным подходом является сохранение значения в [закрытой](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной на том же уровне, что и свойство. Необходимо определить `Get` процедуру внутри свойства, к которому она применяется.  
  
 `Get` процедура по умолчанию имеет уровень доступа содержащего его свойства, если в инструкции `Get` не используется `accessmodifier`.  
  
## <a name="rules"></a>Правила  
  
- **Уровни смешанного доступа.** Если вы определяете свойство для чтения и записи, при необходимости можно указать другой уровень доступа либо для `Get`, либо для `Set` процедуры, но не для обоих. В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Get` процедуру `Private`, но не `Public`.  
  
     При определении свойства `ReadOnly` `Get` процедура представляет все свойство. Нельзя объявить другой уровень доступа для `Get`, так как для свойства будет задано два уровня доступа.  
  
- **Тип возвращаемого значения.** [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) может объявлять тип данных возвращаемого значения. Процедура `Get` автоматически возвращает этот тип данных. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.  
  
     Если в инструкции `Property` не указано `returntype`, процедура возвращает `Object`.  
  
## <a name="behavior"></a>Поведение  
  
- **Возврат из процедуры.** Когда `Get` процедура возвращается в вызывающий код, выполнение продолжится в операторе, который запросил значение свойства.  
  
     `Get` процедуры свойств могут возвращать значение с помощью [оператора return](../../../visual-basic/language-reference/statements/return-statement.md) или путем присвоения возвращаемого значения имени свойства. Дополнительные сведения см. в разделе "возвращаемое значение" в [операторе Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства. Любое число инструкций `Exit Property` и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` и `Return` операторы.  
  
- **Возвращаемое значение.** Чтобы вернуть значение из `Get` процедуры, можно либо присвоить значение имени свойства, либо включить его в [оператор return](../../../visual-basic/language-reference/statements/return-statement.md). Оператор `Return` одновременно присваивает возвращаемое значение хранимой процедуры `Get` и завершает процедуру.  
  
     Если вы используете `Exit Property` без присвоения значения имени свойства, процедура `Get` возвращает значение по умолчанию для типа данных свойства. Дополнительные сведения см. в разделе "возвращаемое значение" в [операторе Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     В следующем примере показаны два способа, которым свойство только для чтения `quoteForTheDay` может возвращать значение, удерживаемое в закрытой переменной `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Get` используется для получения значения свойства.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>См. также

- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Пошаговое руководство. Определение классов](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
