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
ms.openlocfilehash: ab18a7137a31ed8e616f465e7d617305c96d7b10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943021"
---
# <a name="-operator-visual-basic"></a>Оператор + (Visual Basic)
Складывает два числа или возвращает положительное значение числового выражения. Также можно использовать для сцепления двух строковых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression1`|Обязательный. Любое числовое или строковое выражение.|  
|`expression2`|Требуется, `+` если оператор не вычисляет отрицательное значение. Любое числовое или строковое выражение.|  
  
## <a name="result"></a>Результат  
 Если `expression1` и`expression2` являются числовыми, результатом является их арифметическая сумма.  
  
 Если `expression2` параметр отсутствует `+` , оператор является унарным оператором идентификации для неизменного значения выражения. В этом смысле операция состоит из удержания знака `expression1`, поэтому результат будет отрицательным, если `expression1` имеет отрицательное значение.  
  
 Если `expression1` и`expression2` являются строками, результатом является объединение их значений.  
  
 Если `expression1` и`expression2` имеют смешанные типы, то выполняемое действие зависит от их типов, их содержимого и значения, установленного в [операторе Option](../../../visual-basic/language-reference/statements/option-strict-statement.md). Дополнительные сведения см. в таблицах в разделе "Примечания".  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая неподписанные и типы `Decimal`с плавающей запятой `String`, и.  
  
## <a name="remarks"></a>Примечания  
 Как правило, `+` выполняет арифметическое сложение, когда это возможно, и объединяет только в том случае, если оба выражения являются строками.  
  
 Если ни одно из выражений `Object`не является, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба выражения являются числовыми типами данных`SByte`( `Byte` `Short`,, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, ,`Decimal` ,`Single`или )`Double`.|Включить. Тип данных result является числовым типом, подходящим для типов `expression1` данных и. `expression2` См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип`String`|Объединения.|  
|Одно выражение является числовым типом данных, а второй — строкой|Если `Option Strict` имеет `On`значение, то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет `Off`значение, `String` то неявнопреобразует`Double` в и добавьте.<br /><br /> Если не удается преобразовать в `Double`, вызовите <xref:System.InvalidCastException> исключение. `String`|  
|Одно выражение имеет числовой тип данных, а другой — [Nothing](../../../visual-basic/language-reference/nothing.md) .|Добавьте со `Nothing` значением 0.|  
|Одно выражение — строка, а другая —`Nothing`|Объединение со `Nothing` значением "".|  
  
 Если одно выражение является `Object` выражением, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|`Object`выражение содержит числовое значение, а другое — числовой тип данных|Если `Option Strict` имеет `On`значение, то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет `Off`значение, добавьте.|  
|`Object`выражение содержит числовое значение, а другое имеет тип`String`|Если `Option Strict` имеет `On`значение, то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет `Off`значение, `String` то неявнопреобразует`Double` в и добавьте.<br /><br /> Если не удается преобразовать в `Double`, вызовите <xref:System.InvalidCastException> исключение. `String`|  
|`Object`выражение содержит строку, а другая — числовой тип данных|Если `Option Strict` имеет `On`значение, то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет `Off`значение, то неявно преобразует строку `Object` в `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразована `Double`в, возникает <xref:System.InvalidCastException> исключение.|  
|`Object`выражение содержит строку, а другая — тип`String`|Если `Option Strict` имеет `On`значение, то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет `Off`значение, то неявное `String` преобразование `Object` в и сцепление.|  
  
 Если оба выражения являются `Object` выражениями, Visual Basic выполняет следующие действия (`Option Strict Off` только).  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба `Object` выражения содержат числовые значения|Включить.|  
|Оба `Object` выражения имеют тип`String`|Объединения.|  
|Одно `Object` выражение содержит числовое значение, а другое содержит строку.|Неявным образом преобразуйте `Double` строку `Object` в и добавьте.<br /><br /> Если строка `Object` не может быть преобразована в числовое значение, то <xref:System.InvalidCastException> возникает исключение.|  
  
 Если любое `Object` из выражений имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md) или <xref:System.DBNull> `String` , `+` оператор обрабатывает его как со значением "".  
  
> [!NOTE]
> При использовании `+` оператора может быть невозможно определить, будет ли выполняться сложение или объединение строк. `&` Используйте оператор для объединения, чтобы исключить неоднозначность и предоставить код для самостоятельного документирования.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `+` Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `+` оператор используется для добавления чисел. Если операнды являются числовыми, Visual Basic вычислит арифметический результат. Арифметический результат представляет сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 Можно также использовать `+` оператор для сцепления строк. Если операнды являются строками, Visual Basic сцепляет их. Результат объединения представляет собой одну строку, состоящую из содержимого двух операндов, один за другим.  
  
 Если операнды имеют смешанные типы, результат зависит от значения параметра [Option Case](../../../visual-basic/language-reference/statements/option-strict-statement.md). В следующем примере показан результат, если `Option Strict` имеет `On`значение.  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 В следующем примере показан результат, если `Option Strict` имеет `Off`значение.  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Чтобы избежать неоднозначности, следует использовать `&` оператор `+` вместо для объединения.  
  
## <a name="see-also"></a>См. также

- [Оператор &](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Операторы объединения](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Арифметические операторы](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Арифметические операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
