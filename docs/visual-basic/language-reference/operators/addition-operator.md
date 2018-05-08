---
title: + Оператор (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: ccf79c700cf852c0febb9c3f3464cbacdd39296e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>Оператор + (Visual Basic)
Складывает два числа или возвращает положительное значение числового выражения. Может также использоваться для сцепления двух строковых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression1`|Обязательно. Числовое или строковое выражение.|  
|`expression2`|Требуется, если `+` оператор вычисляет отрицательное значение. Числовое или строковое выражение.|  
  
## <a name="result"></a>Результат  
 Если `expression1` и `expression2` оба, являются числовыми, результатом является их арифметическая сумма.  
  
 Если `expression2` отсутствует, `+` оператор *унарный* оператором идентификатора для неизменяемого значения выражения. В этом смысле операция представляет собой сохранение знака `expression1`, поэтому результат будет отрицательным Если `expression1` является отрицательным значением.  
  
 Если `expression1` и `expression2` представляют собой строки, результатом является объединением их значения.  
  
 Если `expression1` и `expression2` , смешанных типов действия зависят от их типов, их содержимое и значения [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md). Дополнительные сведения содержатся в таблицах раздела «Примечания».  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`, и `String`.  
  
## <a name="remarks"></a>Примечания  
 В общем случае `+` выполняет арифметического сложения, когда это возможно и объединяет только в том случае, если оба выражения являются строками.  
  
 Если ни одно из выражений `Object`, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие компилятора|  
|---|---|  
|Оба выражения имеют числовые типы данных (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, или `Double`)|Добавите. Тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`. В таблице «Целочисленных арифметических операций» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип `String`|Объединение.|  
|Одно выражение является числовым типом данных, а другой — строка|Если `Option Strict` — `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразовать `String` для `Double` и добавьте.<br /><br /> Если `String` не может быть преобразован `Double`, создается исключение <xref:System.InvalidCastException> исключение.|  
|Одно выражение является числовым типом данных, а другой — [Nothing](../../../visual-basic/language-reference/nothing.md)|Добавить, с `Nothing` табличные значения как ноль.|  
|Одно выражение представляет собой строку, а другой — `Nothing`|Объединение с `Nothing` значениями, как «».|  
  
 Если одно из выражений является `Object` выражения, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие компилятора|  
|---|---|  
|`Object` выражение содержит числовое значение, а другой — числовой тип данных|Если `Option Strict` — `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, затем добавьте.|  
|`Object` выражение содержит числовое значение, а другой — типа `String`|Если `Option Strict` — `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразовать `String` для `Double` и добавьте.<br /><br /> Если `String` не может быть преобразован `Double`, создается исключение <xref:System.InvalidCastException> исключение.|  
|`Object` выражение содержит строку, а другой — числовой тип данных|Если `Option Strict` — `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразует строку `Object` для `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразован `Double`, создается исключение <xref:System.InvalidCastException> исключение.|  
|`Object` выражение содержит строку, а другой — типа `String`|Если `Option Strict` — `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразовать `Object` для `String` и соединения.|  
  
 Если оба выражения имеют `Object` выражения, Visual Basic выполняет следующие действия (`Option Strict Off` только).  
  
|Типы данных выражений|Действие компилятора|  
|---|---|  
|Оба `Object` выражения содержат числовые значения|Добавите.|  
|Оба `Object` выражения имеют тип `String`|Объединение.|  
|Один `Object` выражение содержит числовое значение, а другое содержит строку|Неявно преобразует строку `Object` для `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразован в числовое значение, а затем вызывать <xref:System.InvalidCastException> исключение.|  
  
 Если параметр `Object` выражение, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md) или <xref:System.DBNull>, `+` оператор воспринимает его как `String` со значением «».  
  
> [!NOTE]
>  При использовании `+` оператор не можно определить, произойдет ли объединение строк или сложение операция. Используйте `&` для объединения оператор во избежание неоднозначности и выполнять код.  
  
## <a name="overloading"></a>Перегрузка  
 `+` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `+` оператора для сложения чисел. Если оба операнда являются числовыми, Visual Basic вычисляет арифметический результат. Арифметический результат возвращает сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 Можно также использовать `+` оператор для объединения строк. Если оба операнда являются строками, Visual Basic объединяет их. Результат объединения представляет одну строку, состоящую из содержимого двух операндов один за другим.  
  
 Если операнды имеют разных типов, результат зависит от настройки [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md). В следующем примере показан результат при `Option Strict` — `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 В следующем примере показан результат при `Option Strict` — `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 Чтобы избежать неоднозначности, следует использовать `&` оператор вместо `+` для объединения.  
  
## <a name="see-also"></a>См. также  
 [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
