---
title: Инструкция Set (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b18e6c858e64e78d7ab85fdaafd70e510f7a02f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 Необязательно. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Необязательный на более одного `Get` и `Set` инструкции в этом свойстве. Ниже указаны доступные значения.  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Обязательный. Параметр, содержащий новое значение для свойства.  
  
 `datatype`  
 Обязателен, если `Option Strict` — `On`. Тип данных `value` параметра. Указанный тип данных должен быть таким же, как тип данных свойства, где это `Set` оператор объявлен.  
  
 `statements`  
 Необязательно. Один или несколько операторов, выполняемых при `Set` вызывается процедура свойства.  
  
 `End Set`  
 Обязательный. Завершает определение `Set` процедуры свойства.  
  
## <a name="remarks"></a>Примечания  
 Каждое свойство должно иметь `Set` процедуры свойства, если свойство помечено как `ReadOnly`. `Set` Процедура используется для задания значения свойства.  
  
 Visual Basic автоматически вызывает свойство `Set` процедуру, когда оператор присваивания предоставляет значение хранится в свойстве.  
  
 Visual Basic передает параметр `Set` процедуры во время назначения свойств. Если не указать параметр для `Set`, интегрированной среды разработки (IDE) использует неявный параметр с именем `value`. Параметр содержит значение, присваиваемое свойству. Обычно сохраните значение в частной локальной переменной и возвращается при каждом `Get` при вызове процедуры.  
  
 Тело объявления свойства может содержать только свойства `Get` и `Set` процедур между [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) и `End Property` инструкции. Оно не может хранить ничего, кроме этих процедур. В частности он не может хранить текущее значение свойства. Это значение за пределами свойства, необходимо сохранить, поскольку при сохранении внутри любой из процедур свойства, процедуры свойства не может получить доступ к его. Обычный способ — хранить значение в [закрытый](../../../visual-basic/language-reference/modifiers/private.md) переменной, объявленной в том же уровне, что и свойство. Необходимо определить `Set` процедуры внутри свойства, к которому он применяется.  
  
 `Set` Процедуры по умолчанию устанавливается уровень доступа свойства, содержащего Если вы используете `accessmodifier` в `Set` инструкции.  
  
## <a name="rules"></a>Правила  
  
-   **Смешанные уровни доступа.** При определении свойства чтения и записи, при необходимости можно указать другой уровень доступа для любого `Get` или `Set` процедуры, но не оба. После этого уровень доступа процедуры должен быть более ограничивающим, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедура `Private`, но не `Public`.  
  
     При определении `WriteOnly` свойства `Set` процедура представляет все свойство. Нельзя объявлять разные права доступа уровня для `Set`, так как это установит два уровня доступа для свойства.  
  
## <a name="behavior"></a>Поведение  
  
-   **Возвращение из процедуры свойства.** Когда `Set` процедура возвращает в вызывающий код, выполнение продолжается после инструкции, которая предоставляет значение для сохранения.  
  
     `Set`процедуры свойств можно вернуть с помощью [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) или [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     `Exit Property` И `Return` инструкции вызывают Немедленный выход из процедуры свойства. Любое количество `Exit Property` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Property` и `Return` инструкции.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Set` инструкции, чтобы задать значение свойства.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
