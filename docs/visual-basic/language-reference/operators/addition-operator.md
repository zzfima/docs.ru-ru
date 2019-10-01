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
ms.openlocfilehash: 3187551afb7d25470f48dad894188766a811bb0a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701001"
---
# <a name="-operator-visual-basic"></a>Оператор + (Visual Basic)
Складывает два числа или возвращает положительное значение числового выражения. Также можно использовать для сцепления двух строковых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
expression1 + expression2
```
  
или

```vb  
+expression1  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression1`|Обязательный. Любое числовое или строковое выражение.|  
|`expression2`|Требуется, если оператор `+` не вычисляет отрицательное значение. Любое числовое или строковое выражение.|  
  
## <a name="result"></a>Результат  
 Если `expression1` и `expression2` являются числовыми, то результатом будет их арифметическая сумма.  
  
 Если `expression2` отсутствует, оператор `+` является *унарным* оператором Identity для неизмененного значения выражения. В этом смысле операция состоит в том, чтобы хранить знак `expression1`, поэтому результат будет отрицательным, если `expression1` отрицательный.  
  
 Если `expression1` и `expression2` являются строками, результатом будет объединение их значений.  
  
 Если `expression1` и `expression2` имеют смешанные типы, то выполняемое действие зависит от их типов, содержимого и значения параметра [Option Case](../../../visual-basic/language-reference/statements/option-strict-statement.md). Дополнительные сведения см. в таблицах в разделе "Примечания".  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая неподписанные и типы с плавающей запятой, а также `Decimal` и `String`.  
  
## <a name="remarks"></a>Примечания  
 Как правило, `+` выполняет арифметическое сложение, когда это возможно, и объединяет только в том случае, если оба выражения являются строками.  
  
 Если ни одно из выражений не является `Object`, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба выражения являются числовыми типами данных (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong` или 0).|Включить. Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип `String`|Объединения.|  
|Одно выражение является числовым типом данных, а второй — строкой|Если `Option Strict` равно `On`, то возникает ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, неявно преобразуйте `String` в `Double` и добавьте.<br /><br /> Если `String` невозможно преобразовать в `Double`, то вызовите исключение <xref:System.InvalidCastException>.|  
|Одно выражение имеет числовой тип данных, а другой — [Nothing](../../../visual-basic/language-reference/nothing.md) .|Добавьте с `Nothing` с нулевым значением.|  
|Одно выражение является строкой, а другое — `Nothing`.|Объединение с `Nothing` со значением "".|  
  
 Если одно из выражений является выражением `Object`, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|выражение `Object` содержит числовое значение, а другое — числовой тип данных|Если `Option Strict` равно `On`, то возникает ошибка компилятора.<br /><br /> Если `Option Strict` равно `Off`, добавьте.|  
|выражение `Object` содержит числовое значение, а другое имеет тип `String`|Если `Option Strict` равно `On`, то возникает ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, неявно преобразуйте `String` в `Double` и добавьте.<br /><br /> Если `String` невозможно преобразовать в `Double`, то вызовите исключение <xref:System.InvalidCastException>.|  
|выражение `Object` содержит строку, а другая — числовой тип данных.|Если `Option Strict` равно `On`, то возникает ошибка компилятора.<br /><br /> Если `Option Strict` равно `Off`, то неявным образом Преобразуйте строку `Object` в `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразована в `Double`, то возникает исключение <xref:System.InvalidCastException>.|  
|выражение `Object` содержит строку, а другая — тип `String`|Если `Option Strict` равно `On`, то возникает ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off`, неявно преобразуйте `Object` в `String` и объедините.|  
  
 Если оба выражения являются выражениями `Object`, Visual Basic выполняет следующие действия (только `Option Strict Off`).  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба выражения `Object` содержат числовые значения|Включить.|  
|Оба выражения `Object` имеют тип `String`|Объединения.|  
|Одно выражение `Object` содержит числовое значение, а другое содержит строку.|Неявным образом Преобразуйте строку `Object` в `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразована в числовое значение, то возникает исключение <xref:System.InvalidCastException>.|  
  
 Если выражение `Object` имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md) или <xref:System.DBNull>, оператор `+` обрабатывает его как `String` со значением "".  
  
> [!NOTE]
> При использовании оператора `+` может оказаться невозможной определить, будет ли выполняться сложение или объединение строк. Используйте оператор `&` для объединения, чтобы избежать неоднозначности и предоставить код для самостоятельного документирования.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `+` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `+` используется для добавления чисел. Если операнды являются числовыми, Visual Basic вычислит арифметический результат. Арифметический результат представляет сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 Для сцепления строк можно также использовать оператор `+`. Если операнды являются строками, Visual Basic сцепляет их. Результат объединения представляет собой одну строку, состоящую из содержимого двух операндов, один за другим.  
  
 Если операнды имеют смешанные типы, результат зависит от значения параметра [Option Case](../../../visual-basic/language-reference/statements/option-strict-statement.md). В следующем примере показан результат, если `Option Strict` равно `On`.  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 В следующем примере показан результат, если `Option Strict` равно `Off`.  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Чтобы избежать неоднозначности, следует использовать оператор `&` вместо `+` для объединения.  
  
## <a name="see-also"></a>См. также

- [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
