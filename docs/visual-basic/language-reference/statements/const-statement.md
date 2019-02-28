---
title: Оператор Const (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: eb99213287cda5ce7f9c3afe2998efb02ec68a03
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979077"
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
 Необязательный параметр. Список атрибутов, применяемых к все константы, объявленных в этой инструкции. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) в угловые скобки (»`<`«и»`>`«).  
  
 `accessmodifier`  
 Необязательный параметр. Позволяет указать, какой код может обращаться к эти константы. Может быть [открытый](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [частных](../../../visual-basic/language-reference/modifiers/private.md), или [Private Protected](../../language-reference/modifiers/private-protected.md).
  
 `Shadows`  
 Необязательный параметр. Используется для повторного объявления и скрыть программный элемент в базовом классе. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Обязательный. Список констант, объявляемых в данной инструкции.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Каждый элемент `constant` имеет перечисленные ниже синтаксис и компоненты.  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Отделение|Описание:|  
|----------|-----------------|  
|`constantname`|Обязательный. Имя константы. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Обязателен, если `Option Strict` является `On`. Тип данных константы.|  
|`initializer`|Обязательный. Выражение, которое вычисляется во время компиляции и присваиваемое константе.|  
  
## <a name="remarks"></a>Примечания  
 Если в приложении значение, которое никогда не изменяется, можно определить именованную константу и использовать его вместо литеральных значений. Имя проще запомнить, чем значение. Можно определить константу только один раз и использовать его во многих местах в коде. Если в более поздней версии, вам нужно переопределить значение, `Const` оператор является единственным местом, необходимо внести изменения.  
  
 Можно использовать `Const` только на уровне модуля или процедуры. Это означает, что *контекст объявления* для переменной должен быть класс, структура, модуль, процедуры или блока, а не может быть исходный файл, пространство имен или интерфейс. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Локальные константы (внутри процедуры) по умолчанию для общего доступа и невозможно использовать модификаторы доступа на них. Класс и модуль член константы (вне любых процедур) по умолчанию закрытый доступ, а константы-члены структуры по умолчанию общий доступ. Вы можете настроить уровни доступа с помощью модификаторов доступа.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Константа объявлен на уровне модуля, вне любых процедур является *член константы*; он является членом класса, структуры, или модуль, они объявлены.  
  
     Константе, объявленной на уровне процедуры является *локальная константа*; она является локальной для процедуры или блока, объявляющему его.  
  
-   **Атрибуты.** Атрибуты можно применить только к член константы, а не к локальной константы. Атрибут вносит сведения для метаданных сборки, которая не имеет смысла для временного хранения, такие как локальные константы.  
  
-   **Модификаторы.** По умолчанию, все константы `Shared`, `Static`, и `ReadOnly`. Эти ключевые слова нельзя использовать при объявлении константы.  
  
     На уровне процедуры, нельзя использовать `Shadows` или любое обращение модификаторы для объявления локальной константы.  
  
-   **Несколько констант.** Можно объявить несколько констант в одном операторе объявления, указав `constantname` часть для каждого из них. Несколько констант разделяются запятыми.  
  
## <a name="data-type-rules"></a>Правила для типа данных  
  
-   **Типы данных.** `Const` Инструкции можно объявить тип данных переменной. Можно указать любой тип данных или имя перечисления.  
  
-   **Тип по умолчанию.** Если вы не укажете `datatype`, константа имеет тип данных `initializer`. Если задан и `datatype` и `initializer`, тип данных `initializer` должно быть преобразуемым в `datatype`. Если ни один из `datatype` , ни `initializer` присутствует, по умолчанию тип данных `Object`.  
  
-   **Различные типы.** Можно указать различные типы данных для различных констант с помощью отдельных `As` предложение для каждой объявляемой переменной. Тем не менее, нельзя объявлять несколько констант одного типа с помощью общего `As` предложение.  
  
-   **Инициализация.** Необходимо инициализировать значение каждой константы в `constantlist`. Использовании `initializer` позволяет указать выражение для назначения константе. Выражение может быть любое сочетание литералов, другие константы, которые уже определены и членов перечисления, которые уже определены. Арифметические и логические операторы можно использовать для объединения этих элементов.  
  
     Нельзя использовать переменные или функции в `initializer`. Тем не менее, можно использовать ключевое слово преобразования, такие как `CByte` и `CShort`. Можно также использовать `AscW` при ее вызове с константой `String` или `Char` аргумент, поскольку, может быть вычислено во время компиляции.  
  
## <a name="behavior"></a>Поведение  
  
-   **Область.** Локальные константы будут доступны только в пределах их процедуры или блока. Член константы доступны из любого места внутри их класса, структуры или модуля.  
  
-   **Квалификации.** Код вне класса, структуры или модуля необходимо указать имя константы-члена с именем этого класса, структуры или модуля. Код за пределами процедуры или блока не может ссылаться на любые локальные константы в рамках этой процедуры или блока.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Const` инструкцию для объявления констант для использования вместо литеральных значений.  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a>Пример  
 Если определить константу с типом данных `Object`, компилятор Visual Basic предоставляет тип `initializer`, а не `Object`. В следующем примере, константа `naturalLogBase` имеет тип времени выполнения `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 В предыдущем примере используется <xref:System.Type.ToString%2A> метод <xref:System.Type> объект, возвращаемый [оператор GetType](../../../visual-basic/language-reference/operators/gettype-operator.md), так как <xref:System.Type> невозможно преобразовать в `String` с помощью `CStr`.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Константы и перечисления](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Константы и перечисления](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
