---
title: Инструкция Set (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: cb0dc76d110f3e6a3ea3e74cc0bfb5a669b35396
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583239"
---
# <a name="set-statement-visual-basic"></a>Инструкция Set (Visual Basic)
Объявляет процедуру свойства `Set`, используемую для присвоения значения свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательный. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 (Необязательно) не более одного из инструкций `Get` и `Set` в этом свойстве. Ниже указаны доступные значения.  
  
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Обязательный. Параметр, содержащий новое значение свойства.  
  
 `datatype`  
 Требуется, если `Option Strict` `On`. Тип данных параметра `value`. Указанный тип данных должен совпадать с типом данных свойства, в котором объявлена эта `Set`ая инструкция.  
  
 `statements`  
 Необязательный. Одна или несколько инструкций, выполняемых при вызове процедуры свойства `Set`.  
  
 `End Set`  
 Обязательный. Завершает определение процедуры свойства `Set`.  
  
## <a name="remarks"></a>Заметки  
 Каждое свойство должно иметь `Set` процедуру свойства, если только свойство не помечено как `ReadOnly`. Процедура `Set` используется для задания значения свойства.  
  
 Visual Basic автоматически вызывает процедуру `Set` свойства, когда оператор присваивания предоставляет значение, которое должно храниться в свойстве.  
  
 Visual Basic передает параметр в процедуру `Set` во время назначения свойств. Если параметр для `Set` не указан, в интегрированной среде разработки (IDE) используется неявный параметр с именем `value`. Параметр содержит значение, присваиваемое свойству. Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом вызове процедуры `Get`.  
  
 Тело объявления свойства может содержать только `Get` и `Set` процедуры свойства между [оператором Property](../../../visual-basic/language-reference/statements/property-statement.md) и оператором `End Property`. Он не может хранить ничего, Кроме этих процедур. В частности, он не может хранить текущее значение свойства. Это значение необходимо хранить за пределами свойства, так как при хранении в любой из процедур свойств другая процедура свойства не может получить к ней доступ. Обычным подходом является сохранение значения в [закрытой](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной на том же уровне, что и свойство. Необходимо определить `Set` процедуру внутри свойства, к которому она применяется.  
  
 @No__t_0 процедура по умолчанию имеет уровень доступа содержащего его свойства, если в инструкции `Set` не используется `accessmodifier`.  
  
## <a name="rules"></a>Правила  
  
- **Уровни смешанного доступа.** Если вы определяете свойство для чтения и записи, при необходимости можно указать другой уровень доступа либо для `Get`, либо для `Set` процедуры, но не для обоих. В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедуру `Private`, но не `Public`.  
  
     При определении свойства `WriteOnly` `Set` процедура представляет все свойство. Нельзя объявить другой уровень доступа для `Set`, так как для свойства будет задано два уровня доступа.  
  
## <a name="behavior"></a>Поведение  
  
- **Возврат из процедуры свойства.** Когда процедура `Set` возвращается в вызывающий код, выполнение продолжится после оператора, который предоставил значение для сохранения.  
  
     `Set` процедуры свойств могут возвращаться с помощью [оператора return](../../../visual-basic/language-reference/statements/return-statement.md) или [оператора Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства. Любое число инструкций `Exit Property` и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` и `Return` операторы.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Set` используется для задания значения свойства.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>См. также

- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
