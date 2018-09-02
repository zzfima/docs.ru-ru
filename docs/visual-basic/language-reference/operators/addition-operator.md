---
title: + Operator (Visual Basic)
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
ms.openlocfilehash: 91806c204c313956b292eb9c9be078991f733b4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420906"
---
# <a name="-operator-visual-basic"></a>Оператор + (Visual Basic)
Складывает два числа и возвращает положительное значение числового выражения. Может также использоваться для сцепления двух строковых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression1`|Обязательно. Числовым или строковым выражением.|  
|`expression2`|Требуется, если `+` оператор вычисляет отрицательное значение. Числовым или строковым выражением.|  
  
## <a name="result"></a>Результат  
 Если `expression1` и `expression2` оба являются числового, результатом является их арифметическая сумма.  
  
 Если `expression2` отсутствует, `+` оператор *унарный* оператор удостоверения для неизменное значение выражения. В этом смысле операция представляет собой сохранение знака `expression1`, поэтому результат будет отрицательным Если `expression1` является отрицательным.  
  
 Если `expression1` и `expression2` строки, результатом является объединение их значения.  
  
 Если `expression1` и `expression2` , смешанные типы действия зависит от их типов, их содержимое и значения [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md). Дополнительные сведения см. в таблицах в подразделе «Примечания».  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая типы без знака и с плавающей запятой и `Decimal`, и `String`.  
  
## <a name="remarks"></a>Примечания  
 В общем случае `+` выполняет арифметического сложения, когда это возможно и объединяет только в том случае, если оба выражения имеют строки.  
  
 Если ни одно из выражений `Object`, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие компилятора|  
|---|---|  
|Оба выражения имеют числовые типы данных (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, или `Double`)|Добавите. Тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`. См. в таблицах «Целочисленных арифметических операций» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип `String`|Объединение.|  
|Одного из выражений имеет числовой тип данных, а другой — строка|Если `Option Strict` является `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразовать `String` для `Double` и добавьте.<br /><br /> Если `String` невозможно преобразовать в `Double`, затем создаст исключение <xref:System.InvalidCastException> исключение.|  
|Одного из выражений имеет числовой тип данных, а другой — [Nothing](../../../visual-basic/language-reference/nothing.md)|Добавить, с помощью `Nothing` табличные значения как ноль.|  
|Одно выражение является строковым, а другой — `Nothing`|Сцепить с `Nothing` с табличным значением, как «».|  
  
 Если одно выражение имеет тип `Object` выражения, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие компилятора|  
|---|---|  
|`Object` выражение содержит числовое значение, а другой — числовой тип данных|Если `Option Strict` является `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` является `Off`, затем добавьте.|  
|`Object` выражение содержит числовое значение, а другой — типа `String`|Если `Option Strict` является `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразовать `String` для `Double` и добавьте.<br /><br /> Если `String` невозможно преобразовать в `Double`, затем создаст исключение <xref:System.InvalidCastException> исключение.|  
|`Object` выражение содержит строку, а другой — числовой тип данных|Если `Option Strict` является `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразует строку `Object` для `Double` и добавьте.<br /><br /> Если строка `Object` невозможно преобразовать в `Double`, затем создаст исключение <xref:System.InvalidCastException> исключение.|  
|`Object` выражение содержит строку, а другой — типа `String`|Если `Option Strict` является `On`, затем создает ошибку компилятора.<br /><br /> Если `Option Strict` — `Off`, неявно преобразовать `Object` для `String` и соединения.|  
  
 Если оба выражения имеют `Object` выражения, Visual Basic выполняет следующие действия (`Option Strict Off` только).  
  
|Типы данных выражений|Действие компилятора|  
|---|---|  
|Оба `Object` выражения хранение числовых значений|Добавите.|  
|Оба `Object` выражения имеют тип `String`|Объединение.|  
|Один `Object` выражение содержит числовое значение, а другое содержит строку|Неявно преобразует строку `Object` для `Double` и добавьте.<br /><br /> Если строка `Object` невозможно преобразовать в числовые значения, а затем вызывать <xref:System.InvalidCastException> исключение.|  
  
 Если параметр `Object` выражение, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md) или <xref:System.DBNull>, `+` оператор воспринимает его как `String` со значением «».  
  
> [!NOTE]
>  При использовании `+` оператора, может не появиться возможность определить, произойдет ли объединение строк или сложение операция. Используйте `&` для объединения оператор устранения неоднозначности и выполнять код.  
  
## <a name="overloading"></a>Перегрузка  
 `+` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `+` оператора для сложения чисел. Если оба операнда являются числовыми, Visual Basic вычисляет арифметический результат. Арифметический результат возвращает сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 Можно также использовать `+` оператор для объединения строк. Если оба операнда являются строками, Visual Basic объединяет их. Результат объединения представляет одну строку, состоящую из содержимого двух операндов один за другим.  
  
 Если операнды имеют разных типов, результат зависит от параметра [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md). В следующем примере показан результат при `Option Strict` является `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 В следующем примере показан результат при `Option Strict` является `Off`.  
  
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
