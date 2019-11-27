---
title: + оператора
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
ms.openlocfilehash: 12c14b3be0562a31470ddbd2d5489ccdbdf3b62b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350294"
---
# <a name="-operator-visual-basic"></a>Оператор + (Visual Basic)
Складывает два числа или возвращает положительное значение числового выражения. Также можно использовать для сцепления двух строковых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
expression1 + expression2
```
  
или диспетчер конфигурации служб

```vb  
+expression1  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression1`|Обязательно. Любое числовое или строковое выражение.|  
|`expression2`|Требуется, если оператор `+` не вычисляет отрицательное значение. Любое числовое или строковое выражение.|  
  
## <a name="result"></a>Результат  
 Если `expression1` и `expression2` являются числовыми, то результатом является их арифметическая сумма.  
  
 Если `expression2` отсутствует, оператор `+` является *унарным* оператором Identity для неизмененного значения выражения. В этом смысле операция состоит в том, чтобы хранить знак `expression1`, поэтому результат будет отрицательным, если `expression1` отрицательный.  
  
 Если `expression1` и `expression2` являются строками, результатом будет объединение их значений.  
  
 Если `expression1` и `expression2` имеют смешанные типы, выполняемое действие зависит от их типов, их содержимого и значения, установленного в [операторе Option](../../../visual-basic/language-reference/statements/option-strict-statement.md). Дополнительные сведения см. в таблицах в разделе "Примечания".  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Все числовые типы, включая неподписанные и типы с плавающей запятой, а также `Decimal`и `String`.  
  
## <a name="remarks"></a>Заметки  
 В целом `+` выполняет арифметическое сложение, когда это возможно, и объединяет только в том случае, если оба выражения являются строками.  
  
 Если ни одно из выражений не является `Object`, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба выражения являются числовыми типами данных (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`или `Double`).|Добавить Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2`. См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Оба выражения имеют тип `String`|Объединения.|  
|Одно выражение является числовым типом данных, а второй — строкой|Если `Option Strict` `On`, создайте ошибку компилятора.<br /><br /> Если `Option Strict` `Off`, неявно преобразуйте `String` в `Double` и добавьте.<br /><br /> Если `String` невозможно преобразовать в `Double`, вызовите исключение <xref:System.InvalidCastException>.|  
|Одно выражение имеет числовой тип данных, а другой — [Nothing](../../../visual-basic/language-reference/nothing.md) .|Добавьте, с `Nothing` значением 0.|  
|Одно выражение — строка, а другая — `Nothing`|Объединение с `Nothing` возвращающий значение "".|  
  
 Если одно выражение является `Object` выражением, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|выражение `Object` содержит числовое значение, а другое — числовой тип данных|Если `Option Strict` `On`, создайте ошибку компилятора.<br /><br /> Если `Option Strict` `Off`, добавьте.|  
|`Object` выражение содержит числовое значение, а другое имеет тип `String`|Если `Option Strict` `On`, создайте ошибку компилятора.<br /><br /> Если `Option Strict` `Off`, неявно преобразуйте `String` в `Double` и добавьте.<br /><br /> Если `String` невозможно преобразовать в `Double`, вызовите исключение <xref:System.InvalidCastException>.|  
|`Object` выражение содержит строку, а другая — числовой тип данных|Если `Option Strict` `On`, создайте ошибку компилятора.<br /><br /> Если `Option Strict` `Off`, то неявное преобразование строкового `Object` в `Double` и добавление.<br /><br /> Если строка `Object` не может быть преобразована в `Double`, вызовите исключение <xref:System.InvalidCastException>.|  
|`Object` выражение содержит строку, а другая — тип `String`|Если `Option Strict` `On`, создайте ошибку компилятора.<br /><br /> Если `Option Strict` `Off`, неявно преобразуйте `Object` в `String` и сцепить.|  
  
 Если оба выражения являются `Object` выражениями, Visual Basic выполняет следующие действия (только для`Option Strict Off`).  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба выражения `Object` содержат числовые значения|Добавить|  
|Оба выражения `Object` имеют тип `String`|Объединения.|  
|Одно `Object` выражение содержит числовое значение, а другое содержит строку.|Неявным образом Преобразуйте строку `Object` в `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразована в числовое значение, возникает исключение <xref:System.InvalidCastException>.|  
  
 Если `Object` выражение имеет значение [Nothing](../../../visual-basic/language-reference/nothing.md) или <xref:System.DBNull>, оператор `+` рассматривает его как `String` со значением "".  
  
> [!NOTE]
> При использовании оператора `+`, возможно, не удастся определить, будет ли выполняться сложение или объединение строк. Используйте оператор `&` для объединения, чтобы избежать неоднозначности и предоставить код для самостоятельного документирования.  
  
## <a name="overloading"></a>Перегрузка  
 Оператор `+` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `+` используется для добавления чисел. Если операнды являются числовыми, Visual Basic вычислит арифметический результат. Арифметический результат представляет сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 Можно также использовать оператор `+` для сцепления строк. Если операнды являются строками, Visual Basic сцепляет их. Результат объединения представляет собой одну строку, состоящую из содержимого двух операндов, один за другим.  
  
 Если операнды имеют смешанные типы, результат зависит от значения параметра [Option Case](../../../visual-basic/language-reference/statements/option-strict-statement.md). В следующем примере показан результат, когда `Option Strict` `On`.  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 В следующем примере показан результат, когда `Option Strict` `Off`.  
  
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
