---
title: "Приоритет операторов в Visual Basic | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arithmetic operators, precedence
- operator precedence
- logical operators, precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators
- operators [Visual Basic], precedence
- precedence, of operators
- comparison operators, precedence
- math operators
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6532fc0c26db3b736c863be075571570a3d25eef
ms.lasthandoff: 03/13/2017

---
# <a name="operator-precedence-in-visual-basic"></a>Порядок применения операторов в Visual Basic
Если несколько операций в выражении, каждая часть вычисляется и разрешить в заранее определенном порядке называется *операторов*.  
  
## <a name="precedence-rules"></a>Приоритет правил  
 Если выражения содержат операторы из более чем одной категории, они вычисляются по следующим правилам:  
  
-   Арифметические операторы и операторы объединения имеют порядок приоритета, описанный в следующем разделе, и все имеют более высокий приоритет, чем сравнения, логические и побитовые операторы.  
  
-   У всех операторов сравнения приоритет одинаковый и имеют более высокий приоритет, чем логические и побитовые операторы, но более низкий приоритет, чем арифметических операторов и операторов объединения.  
  
-   Логические и побитовые операторы имеют порядок приоритета, описанный в следующем разделе, и все имеют более низкий приоритет, чем арифметические, объединения и операторы сравнения.  
  
-   Операторы с одинаковым приоритетом вычисляются слева направо в том порядке, в котором они появляются в выражение.  
  
## <a name="precedence-order"></a>Порядок приоритета  
 Операторы вычисляются в следующем порядке:  
  
### <a name="await-operator"></a>Оператор Await  
 Ожидание  
  
### <a name="arithmetic-and-concatenation-operators"></a>Арифметические операторы и операторы объединения  
 Возведение в степень (`^`)  
  
 Унарный и минус (`+`, `–`)  
  
 Умножение и деление с плавающей запятой (`*`, `/`)  
  
 Целочисленное деление (`\`)  
  
 Арифметический модуль (`Mod`)  
  
 Сложение и вычитание (`+`, `–`)  
  
 Объединение строк (`&`)  
  
 Арифметический сдвиг разряда (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Операторы сравнения  
 All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Логические и побитовые операторы  
 Отрицание (`Not`)  
  
 Вместе (`And`, `AndAlso`)  
  
 Дизъюнкции (`Or`, `OrElse`)  
  
 Исключающего логического сложения (`Xor`)  
  
### <a name="comments"></a>Комментарии  
 `=` Оператор является только оператор сравнения на равенство, не оператор присваивания.  
  
 Оператор объединения строк (`&`) не арифметический оператор, но имеет такой же приоритет группируются с арифметическими операторами.  
  
 `Is` И `IsNot` операторы являются операторами сравнения ссылок объектов. Они не выполняют сравнение значений двух объектов; они проверяют только определить, ссылаются ли две переменные объектов на один экземпляр объекта.  
  
## <a name="associativity"></a>Ассоциативность  
 Когда операторы с одинаковым приоритетом появляются вместе в выражении, например умножение и деление, компилятор вычисляет каждую операцию по порядку слева направо. Это показано в следующем примере.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 Первое выражение вычисляется результат деления 96 / 8 (что в результате дает 12), а затем деления 12 / 4, которая в результате 3. Так как компилятор вычисляет операции для `n1` слева направо оценки зависит от того, порядок явно указывается для `n2`. Оба `n1` и `n2` имеют результат&3;. Напротив `n3` имеет в результате 48, так как круглые скобки заставляют компилятор может вычислить 8 / 4 первого.  
  
 Из-за этого поведения, операторы, называются *левую ассоциативность* в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="overriding-precedence-and-associativity"></a>Переопределение приоритета и ассоциативности  
 Можно использовать скобки для принудительного выполнения некоторых частей выражения раньше других. Это можно переопределить порядок приоритетов и левую ассоциативность. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]всегда выполняет операции, заключенные в скобки, прежде чем за их пределами. Однако в круглые скобки, она поддерживает обычный приоритет и ассоциативность, если не использовать круглые скобки в круглых скобках. Это показано в следующем примере.  
  
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
 [= Оператор](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Оператор LIKE](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Оператор await](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
