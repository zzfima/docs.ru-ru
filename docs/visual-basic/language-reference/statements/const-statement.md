---
title: Оператор Const (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: a5842e284eaa858e7a66160060123edc21858a3a
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233851"
---
# <a name="const-statement-visual-basic"></a>Оператор Const (Visual Basic)
Объявляет и определяет одну или несколько констант.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательный. Список атрибутов, которые применяются ко всем константам, объявляемых в этом операторе. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки («`<`«и»`>`»).  
  
 `accessmodifier`  
 Необязательный. Позволяет указать, какой код может обращаться к этим константам. Может быть [открытый](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [закрытый](../../../visual-basic/language-reference/modifiers/private.md), или [Private Protected](../../language-reference/modifiers/private-protected.md).
  
 `Shadows`  
 Необязательный. Используется для повторного объявления и скрытия программного элемента в базовом классе. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Обязательно. Список констант, объявляемых в этом операторе.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Каждый элемент `constant` имеет перечисленные ниже синтаксис и компоненты.  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Отделение|Описание|  
|----------|-----------------|  
|`constantname`|Обязательно. Имя константы. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Обязателен, если `Option Strict` — `On`. Тип данных константы.|  
|`initializer`|Обязательно. Выражение, которое вычисляется во время компиляции и присваиваемое константе.|  
  
## <a name="remarks"></a>Примечания  
 Если в приложении имеется значение, которое никогда не изменяется, можно определить именованную константу и использовать его вместо литеральных значений. Имя легче запомнить, чем значение. Можно определить константу только один раз и использовать его во многих местах в коде. Если в более поздней версии требуется переопределить значение, `Const` оператор является единственным местом, необходимо внести изменения.  
  
 Можно использовать `Const` только на уровне модуля или процедуры. Это означает *контекст объявления* для переменной должен быть класс, структура, модуль, процедуры или блока и не может быть исходным файлом, пространством имен или интерфейс. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Локальные константы (внутри процедуры) по умолчанию для общего доступа и невозможно использовать модификаторы доступа на них. Класс и модуль члена константы (вне любых процедур) по умолчанию имеют закрытый доступ, а константы-члены структуры по умолчанию общий доступ. Вы можете настроить уровни доступа с помощью модификаторов доступа.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Константа объявленный на уровне модуля, вне любой процедуры *член*; он является членом класса, структуры или модуля, объявляющего его.  
  
     Константа, объявленные на уровне процедуры — *локальная константа*; она является локальной для процедуры или блока, объявляющего его.  
  
-   **Атрибуты.** Атрибуты можно применять только к константам члена, а не к локальной константы. Атрибут вносит сведения для метаданных сборки, которые не имеют смысла для временного хранения, например локальные константы.  
  
-   **Модификаторы.** По умолчанию, все константы `Shared`, `Static`, и `ReadOnly`. Эти ключевые слова нельзя использовать при объявлении константы.  
  
     На уровне процедуры, нельзя использовать `Shadows` или любой доступ модификаторов для объявления локальной константы.  
  
-   **Несколько констант.** Можно объявить несколько констант в одном операторе объявления, указав `constantname` часть для каждого из них. Несколько констант разделяются запятыми.  
  
## <a name="data-type-rules"></a>Правила типов данных  
  
-   **Типы данных.** `Const` Инструкция может объявить тип данных переменной. Можно указать любой тип данных или имя перечисления.  
  
-   **Тип по умолчанию.** Если вы не укажете `datatype`, константа имеет тип данных `initializer`. Если заданы оба `datatype` и `initializer`, тип данных `initializer` должно быть преобразуемым `datatype`. Если ни одна из `datatype` , ни `initializer` присутствует, по умолчанию используется тип данных `Object`.  
  
-   **Различные типы.** Можно указать различные типы данных для разных констант с помощью отдельных `As` предложение для каждой объявляемой переменной. Однако нельзя объявлять несколько констант того же типа с помощью общего `As` предложения.  
  
-   **Инициализация.** Необходимо инициализировать значение каждой константы в `constantlist`. Вы используете `initializer` позволяет указать выражение для назначения константы. Выражение может быть любое сочетание литералов, другие константы, которые уже определены и членов перечисления, которые уже определены. Можно использовать арифметические и логические операторы для объединения этих элементов.  
  
     Нельзя использовать переменные или функции в `initializer`. Тем не менее, можно использовать ключевые слова преобразования, такие как `CByte` и `CShort`. Можно также использовать `AscW` при ее вызове с константой `String` или `Char` аргумент, поскольку, может быть вычислено во время компиляции.  
  
## <a name="behavior"></a>Поведение  
  
-   **Область действия.** Локальные константы доступны только внутри их процедуры или блока. Константы-члены доступны в любом месте в пределах их класса, структуры или модуля.  
  
-   **Квалификация.** Код вне класса, структуры или модуля необходимо определять имя константы-члена с именем этого класса, структуры или модуля. Код за пределами процедуры или блока не может ссылаться на любые локальные константы в пределах этой процедуры или блока.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Const` инструкции для объявления константы для использования вместо литеральных значений.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 Если определить константу с типом данных `Object`, компилятор Visual Basic предоставляет тип `initializer`, а не `Object`. В следующем примере константа `naturalLogBase` имеет тип времени выполнения `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 В предыдущем примере использовался <xref:System.Type.ToString%2A> метод <xref:System.Type> объект, возвращаемый [оператор GetType](../../../visual-basic/language-reference/operators/gettype-operator.md), так как <xref:System.Type> не может быть преобразован `String` с помощью `CStr`.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Константы и перечисления](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
