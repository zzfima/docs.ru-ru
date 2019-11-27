---
title: Приоритет операторов
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 318fcc3f35276ba0b2061ba9677c5fde29429f6f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348281"
---
# <a name="operator-precedence-in-visual-basic"></a>Порядок применения операторов в Visual Basic
Если в выражении встречается несколько операций, каждая часть вычисляется и разрешается в заранее определенном порядке, который называется *приоритетом операторов*.

## <a name="precedence-rules"></a>Правила приоритета
 Если выражения содержат операторы из более чем одной категории, они оцениваются в соответствии со следующими правилами.

- Арифметические и операторы объединения имеют порядок приоритета, описанный в следующем разделе, и имеют более высокий приоритет, чем операторы сравнения, логического и побитового оператора.

- Все операторы сравнения имеют одинаковый приоритет, а все имеют более высокий приоритет, чем логические операторы and, но имеют более низкий приоритет, чем операторы арифметического и объединения.

- Логические и побитовые операторы имеют порядок приоритета, описанный в следующем разделе, и все имеют более низкий приоритет, чем арифметические операторы, операции объединения и сравнения.

- Операторы с одинаковым приоритетом вычисляются слева направо в том порядке, в котором они отображаются в выражении.

## <a name="precedence-order"></a>Порядок очередности
 Операторы оцениваются в следующем порядке приоритета.

### <a name="await-operator"></a>Оператор Await
 Ожидать

### <a name="arithmetic-and-concatenation-operators"></a>Арифметические и операторы объединения
 Возведение в степень (`^`)

 Унарное удостоверение и отрицание (`+`, `–`)

 Умножение и деление с плавающей запятой (`*`, `/`)

 Целочисленное деление (`\`)

 Модульная арифметика (`Mod`)

 Сложение и вычитание (`+`, `–`)

 Объединение строк (`&`)

 Арифметический сдвиг битов (`<<`, `>>`)

### <a name="comparison-operators"></a>Операторы сравнения
 Все операторы сравнения (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)

### <a name="logical-and-bitwise-operators"></a>Логические и побитовые операторы
 Отрицание (`Not`)

 Умножение (`And`, `AndAlso`)

 Включающее сложение (`Or`, `OrElse`)

 Эксклюзивное сложение (`Xor`)

### <a name="comments"></a>Комментарии
 Оператор `=` является только оператором сравнения на равенство, а не оператором присваивания.

 Оператор объединения строк (`&`) не является арифметическим оператором, но в приоритете он сгруппирован с арифметическими операторами.

 Операторы `Is` и `IsNot` являются операторами сравнения ссылок на объекты. Они не сравнивают значения двух объектов; они только определяют, ссылаются ли две объектные переменные на один и тот же экземпляр объекта.

## <a name="associativity"></a>ассоциативностью
 Если операторы с одинаковым приоритетом отображаются вместе в выражении, например умножение и деление, компилятор вычисляет каждую операцию в том виде, в котором она встретилась слева направо. Это показано в следующем примере.

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 Первое выражение вычисляет деление 96/8 (что приводит к 12), а затем деление на 12/4, что приводит к трем. Поскольку компилятор вычисляет операции для `n1` слева направо, вычисление будет таким же, когда порядок явно указывается для `n2`. И `n1`, и `n2` имеют результат 3. Напротив, `n3` имеет результат 48, поскольку круглые скобки заставляют компилятор сначала вычислить 8/4.

 Из-за такого поведения операторы говорят о том, что в Visual Basic не используется *ассоциативность* .

## <a name="overriding-precedence-and-associativity"></a>Переопределение приоритета и ассоциативности
 Можно использовать круглые скобки, чтобы принудительно вычислить некоторые части выражения перед другими. Это может переопределять порядок приоритета и левую ассоциативность. Visual Basic всегда выполняет операции, заключенные в круглые скобки, прежде чем они выходят за пределы. Однако в круглых скобках он поддерживает обычный приоритет и ассоциативность, если в круглых скобках не используются скобки. Это показано в следующем примере.

```vb
Dim a, b, c, d, e, f, g As Double
a = 8.0
b = 3.0
c = 4.0
d = 2.0
e = 1.0
f = a - b + c / d * e
' The preceding line sets f to 7.0. Because of natural operator
' precedence and associativity, it is exactly equivalent to the
' following line.
f = (a - b) + ((c / d) * e)
' The following line overrides the natural operator precedence
' and left associativity.
g = (a - (b + c)) / (d * e)
' The preceding line sets g to 0.5.
```

## <a name="see-also"></a>См. также

- [Оператор =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Оператор Like](../../../visual-basic/language-reference/operators/like-operator.md)
- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Оператор Await](../../../visual-basic/language-reference/operators/await-operator.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
