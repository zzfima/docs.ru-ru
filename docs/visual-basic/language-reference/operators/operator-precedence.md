---
title: Порядок применения операторов в Visual Basic
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
ms.openlocfilehash: 568927eb4759c214311ad34a5b45e28094dd80be
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830036"
---
# <a name="operator-precedence-in-visual-basic"></a>Порядок применения операторов в Visual Basic
Если в выражении несколько операций, каждая часть вычисляется и разрешить в заранее определенном порядке вызывается *порядок применения операторов*.  
  
## <a name="precedence-rules"></a>Правила приоритета  
 Если выражения содержат операторы из более чем одной категории, они вычисляются по следующим правилам:  
  
-   Арифметические операторы и операторы объединения имеют порядок приоритета, описанный в следующем разделе, и все имеют более высокий приоритет, чем сравнения, логические и побитовые операторы.  
  
-   Все операторы сравнения имеют равный приоритет и более высокий приоритет, чем логические и побитовые операторы, но более низкий приоритет, чем арифметические операторы и операторы объединения.  
  
-   Логические и побитовые операторы имеют порядок приоритета, описанный в следующем разделе, и все имеют более низкий приоритет, чем арифметические операции, объединения и операторы сравнения.  
  
-   Операторы с одинаковым приоритетом выполняются в порядке слева направо в порядке, в котором они появляются в выражении.  
  
## <a name="precedence-order"></a>Порядок приоритета  
 Операторы выполняются в следующем порядке:  
  
### <a name="await-operator"></a>Оператор Await  
 Await  
  
### <a name="arithmetic-and-concatenation-operators"></a>Арифметические и операторы объединения  
 Возведение в степень (`^`)  
  
 Унарный и минус (`+`, `–`)  
  
 Умножение и деление с плавающей запятой (`*`, `/`)  
  
 Целочисленное деление (`\`)  
  
 Арифметический модуль (`Mod`)  
  
 Сложение и вычитание (`+`, `–`)  
  
 Объединение строк (`&`)  
  
 Сдвиг битов арифметические (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Операторы сравнения  
 Все операторы сравнения (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Логические и побитовые операторы  
 Отрицание (`Not`)  
  
 Совместно (`And`, `AndAlso`)  
  
 Дизъюнкции (`Or`, `OrElse`)  
  
 Исключающего логического сложения (`Xor`)  
  
### <a name="comments"></a>Комментарии  
 `=` Оператор имеет только оператор сравнения на равенство, не оператор присваивания.  
  
 Оператор объединения строк (`&`) не является арифметический оператор, но в приоритете группируется с арифметическими операторами.  
  
 `Is` И `IsNot` операторы, операторы сравнения объекта ссылки. Они не выполняют сравнение значений двух объектов; они проверяют только определить, ссылаются ли две объектные переменные на один и тот же экземпляр объекта.  
  
## <a name="associativity"></a>Ассоциативность  
 Когда операторы с одинаковым приоритетом появляются вместе в выражении, например, умножение и деление, компилятор вычисляет каждую операцию по порядку слева направо. Это показано в следующем примере.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 Для первого выражения деления 96 / 8 (что приводит к 12), а затем деления 12 / 4, что приводит к трем. Так как компилятор вычисляет операции для `n1` слева направо, вычисление зависит от того, порядок явно указывается для `n2`. Оба `n1` и `n2` имеют результат 3. Напротив `n3` имеет результат 48, так как круглые скобки заставляют компилятор может вычислить 8 / 4 первый.  
  
 Из-за этого поведения, операторы, называются *левую ассоциативность* в Visual Basic.  
  
## <a name="overriding-precedence-and-associativity"></a>Переопределение приоритет и ассоциативность операторов  
 Можно использовать скобки для принудительного выполнения некоторых частей выражения раньше других. Это можно переопределить очередность и ассоциативность слева. Visual Basic всегда выполняет операции, которые заключаются в скобки, прежде чем за их пределами. Тем не менее в скобки, он поддерживает обычный приоритет и ассоциативность операторов, если вы не используете круглые скобки в круглых скобках. Это показано в следующем примере.  
  
```  
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
