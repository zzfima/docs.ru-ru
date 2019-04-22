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
ms.openlocfilehash: 0a8d95ffbabf03a0e6c9d88edb28c248b60f3252
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839084"
---
# <a name="set-statement-visual-basic"></a>Инструкция Set (Visual Basic)
Объявляет `Set` процедуру, которая используется для присвоения значения свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательный параметр. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Необязательно. на более одного `Get` и `Set` инструкций в этом свойстве. Ниже указаны доступные значения.  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Обязательный. Параметр, содержащий новое значение для свойства.  
  
 `datatype`  
 Обязателен, если `Option Strict` является `On`. Тип данных `value` параметра. Тип данных, указанный должны совпадать как тип данных свойства, где это `Set` объявлен оператор.  
  
 `statements`  
 Необязательный параметр. Один или несколько операторов, выполняемых при `Set` вызывается процедура свойства.  
  
 `End Set`  
 Обязательный. Завершает определение `Set` процедуры свойства.  
  
## <a name="remarks"></a>Примечания  
 Каждое свойство должно иметь `Set` процедуры свойства, если свойство помечено `ReadOnly`. `Set` Процедура используется для задания значения свойства.  
  
 Visual Basic автоматически вызывает свойства `Set` процедуре, если оператор присваивания предоставляет значение для сохранения в свойстве.  
  
 Visual Basic передает параметр `Set` процедуры во время назначения свойств. Если не указать параметр для `Set`, интегрированную среду разработки (IDE) использует неявный параметр с именем `value`. Параметр содержит значение, присваиваемое свойству. Обычно вы сохраните это значение в закрытую локальную переменную и вернуть его каждый раз, когда `Get` при вызове процедуры.  
  
 Текст объявления свойства могут содержать только свойства `Get` и `Set` процедур между [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Оно не может хранить ничего, кроме этих процедур. В частности он не может сохранить текущее значение свойства. Необходимо сохранить это значение за пределами свойства, так как при сохранении внутри одной из процедур свойства, другая процедура свойства к нему нет доступа. Обычный способ — хранить значение в [частного](../../../visual-basic/language-reference/modifiers/private.md) переменная, объявленная на том же уровне, так как свойство. Необходимо определить `Set` процедуры внутри свойства, к которому он применяется.  
  
 `Set` Процедуры по умолчанию используется уровень доступа свойства, содержащего только при использовании `accessmodifier` в `Set` инструкции.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанным уровнем доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого, уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедуры `Private`, но не `Public`.  
  
     При определении `WriteOnly` свойства `Set` процедура представляет все свойство. Нельзя объявлять разные права доступа уровня для `Set`, так как это установит два уровня доступа для свойства.  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры свойства.** Когда `Set` процедура возвращает в вызывающий код, выполнение продолжается после инструкции, которая предоставляет значение для сохранения.  
  
     `Set` процедуры свойств можно вернуть с помощью [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) или [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое количество `Exit Property` и `Return` инструкций может находиться в любом в процедуре, и вы можете комбинировать `Exit Property` и `Return` инструкций.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Set` инструкции, чтобы задать значение свойства.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>См. также

- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
