---
title: Операторы C#
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
caps.latest.revision: 40
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a52fad2755c8c255d9489cd7148b0d279c0e1a5e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="c-operators"></a>Операторы C#
C# предоставляет множество операторов, которые являются символами, указывающими, какие операции (математические операции, индексирование, вызов функции и т. д.) следует выполнять в выражении. Вы можете [перегрузить](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md) многие операторы, то есть изменить их значение при применении к некоторому пользовательскому типу.  
  
 Обычно для перечислений (`enum`) разрешены все операции, применимые к целочисленным типам (например, `==`, `!=`, `<`, `>`, `&` и `|`).  
  
 В следующих разделах перечислены операторы C# в порядке убывания приоритета. Операторы в каждом разделе совместно используют один и тот же уровень приоритета.  
 
## <a name="primary-operators"></a>Основные операторы  
 Это операторы с наивысшим приоритетом.
  
 [x.y](../../../csharp/language-reference/operators/member-access-operator.md) — доступ к членам.  
  
 [x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) — доступ к членам с проверкой NULL. Возвращает значение `null`, если левый операнд имеет значение `null`.  
 
 [x?.[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) — доступ к индексам, определяемый условием NULL. Возвращает значение `null`, если левый операнд имеет значение `null`.
 
 [f(x)](../../../csharp/language-reference/operators/invocation-operator.md) — вызов функции.  
  
 [a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) — индексирование агрегатного объекта.  
   
 [x++](../../../csharp/language-reference/operators/increment-operator.md) — постфиксный инкремент. Возвращает значение x и затем обновляет расположение хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).  
  
 [x--](../../../csharp/language-reference/operators/decrement-operator.md) — постфиксный декремент. Возвращает значение x и затем обновляет расположение хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).  
  
 [new](../../../csharp/language-reference/keywords/new-operator.md) – создание экземпляра типа.  
  
 [typeof](../../../csharp/language-reference/keywords/typeof.md) — возвращает объект <xref:System.Type>, представляющий операнд.  
  
 [checked](../../../csharp/language-reference/keywords/checked.md) — включает проверку на переполнение при выполнении операций с целыми числами.  
  
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) — отключает проверку на переполнение при выполнении операций с целыми числами. Это поведение установлено для компилятора по умолчанию.  
  
 [default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) — создает значение типа T по умолчанию.  
  
 [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) — объявляет и возвращает экземпляр делегата.  
  
 [sizeof](../../../csharp/language-reference/keywords/sizeof.md) — возвращает размер в байтах для типа операнда.  
  
 [->](../../../csharp/language-reference/operators/dereference-operator.md) — разыменование указателя в сочетании с доступом к члену.  
  
## <a name="unary-operators"></a>Унарные операторы  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [+x](../../../csharp/language-reference/operators/addition-operator.md) — возвращает значение x.  
  
 [-x](../../../csharp/language-reference/operators/subtraction-operator.md) — числовое отрицание.  
  
 [\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) — логическое отрицание.  
  
 [~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) — поразрядное дополнение.  
  
 [++x](../../../csharp/language-reference/operators/increment-operator.md) — префиксный инкремент. Возвращает значение x после обновления расположения хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).  
  
 [--x](../../../csharp/language-reference/operators/decrement-operator.md) — префиксный декремент. Возвращает значение x после обновления расположения хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).  
  
 [(T)x](../../../csharp/language-reference/operators/invocation-operator.md) — приведение типов.  
  
 [await`Task` — ожидание выполнения ](../../../csharp/language-reference/keywords/await.md).  
  
 [&x](../../../csharp/language-reference/operators/and-operator.md) — получение адреса.  
  
 [*x](../../../csharp/language-reference/operators/multiplication-operator.md) — разыменование.  
  
## <a name="multiplicative-operators"></a>Мультипликативные операторы  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x * y](../../../csharp/language-reference/operators/multiplication-operator.md) — умножение.  
  
 [x / y](../../../csharp/language-reference/operators/division-operator.md) — деление. Если операнды имеют целые числа, результатом является целочисленное значение, усеченное в сторону нуля (например, `-7 / 2 is -3`).  
  
 [x % y](../../../csharp/language-reference/operators/remainder-operator.md) — остаток. Если операнды имеют целые числа, это возвращает остаток от деления x на y.  Если `q = x / y` и `r = x % y`, то `x = q * y + r`.  
  
## <a name="additive-operators"></a>Аддитивные операторы  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x + y](../../../csharp/language-reference/operators/addition-operator.md) — сложение.  
  
 [x – y](../../../csharp/language-reference/operators/subtraction-operator.md) — вычитание.  
  
## <a name="shift-operators"></a>Операторы сдвига  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x <\< y](../../../csharp/language-reference/operators/left-shift-operator.md) — сдвиг битов влево и заполнение правого бита нулем.  
  
 [x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) — сдвиг битов вправо. Если левым операндом является `int` или `long`, затем левые биты заполняются битом знака. Если левым операндом является `uint` или `ulong`, затем левые биты заполняются нулем.  
  
## <a name="relational-and-type-testing-operators"></a>Относительные операторы и операторы тестирования типа  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x \< y](../../../csharp/language-reference/operators/less-than-operator.md) — меньше чем (возвращает true, если x меньше y).  
  
 [x > ](../../../csharp/language-reference/operators/greater-than-operator.md) — больше чем (возвращает true, если x больше y).  
  
 [x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – меньше или равно  
  
 [x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – больше или равно.  
  
 [is](../../../csharp/language-reference/keywords/is.md) — совместимость типов. Возвращает значение true, если вычисленный левый операнд может быть приведен к типу, указанному в правом операнде (статический тип).  
  
 [as](../../../csharp/language-reference/keywords/as.md) — преобразование типов. Возвращает левый операнд, приведенный к типу, заданному правым операндом (статический тип), но `as` возвращает `null`, где `(T)x` вызывает исключение.  
  
## <a name="equality-operators"></a>Операторы равенства  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) — тождество. По умолчанию для ссылочных типов, отличных от `string`, этот оператор возвращает равенство ссылок (проверка удостоверения). Однако типы могут перегрузить `==`, поэтому если планируется проверять удостоверения, лучше использовать метод `ReferenceEquals` для `object`.  
  
 [x != y](../../../csharp/language-reference/operators/not-equal-operator.md) — неравенство. См. примечание для `==`. Если тип перегружает `==`, то его необходимо перегрузить `!=`.  
  
## <a name="logical-and-operator"></a>Оператор логического И  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x & y](../../../csharp/language-reference/operators/and-operator.md) — логическая или битовая операция И. Обычно их можно использовать с целочисленными типами и типами `enum`.  
  
## <a name="logical-xor-operator"></a>Оператор логического исключающего ИЛИ  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x ^ y](../../../csharp/language-reference/operators/xor-operator.md) — логическая или битовая операция исключающего ИЛИ. Обычно их можно использовать с целочисленными типами и типами `enum`.  
  
## <a name="logical-or-operator"></a>Оператор логического ИЛИ  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – логическая или битовая операция ИЛИ. Обычно их можно использовать с целочисленными типами и типами `enum`.  
  
## <a name="conditional-and-operator"></a>Условный оператор И  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) — логическое И. Если первый операнд имеет значение false, то C# не вычисляет второй операнд.  
  
## <a name="conditional-or-operator"></a>Условный оператор ИЛИ  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) — логическое ИЛИ. Если первый операнд имеет значение true, то C# не вычисляет второй операнд.  
  
## <a name="null-coalescing-operator"></a>Оператор объединения с NULL  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x?? y](../../../csharp/language-reference/operators/null-conditional-operator.md) — возвращает `x`, если значение отличается от `null`; в противном случае возвращает `y`.  
  
## <a name="conditional-operator"></a>Условный оператор  
 Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md) — если условие `t` имеет значение true, вычисляет и возвращает `x`, в противном случае вычисляет и возвращает `y`.  
  
## <a name="assignment-and-lambda-operators"></a>Назначение и лямбда-операторы  
 Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.  
  
 [x = y](../../../csharp/language-reference/operators/assignment-operator.md) — назначение.  
  
 [x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) — инкремент. Добавьте значение `y` к значению `x`, сохраните результат в `x` и возвратите новое значение. Если `x` назначает `event`, то `y` должен быть соответствующей функцией, которую C# добавляет в качестве обработчика событий.  
  
 [x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) — декремент. Вычтите значение `y` из значения `x`, сохраните результат в `x` и возвратите новое значение. Если `x` назначает `event`, то `y` должен быть соответствующей функцией, которую C# удаляет в качестве обработчика событий.  
  
 [x *= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) — назначение с умножением. Умножьте значение `y` на значение `x`, сохраните результат в `x` и возвратите новое значение.  
  
 [x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) — назначение с делением. Разделите значение `x` на значение `y`, сохраните результат в `x` и возвратите новое значение.  
  
 [x %= y](../../../csharp/language-reference/operators/remainder-assignment-operator.md) — присваивание остатка. Разделите значение `x` на значение `y`, сохраните остаток в `x` и возвратите новое значение.  
  
 [x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) — назначение с операцией И. Выполните операцию И для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.  
  
 [x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) — назначение с операцией ИЛИ. Выполните операцию ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.  
  
 [x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) — назначение с операцией исключающего ИЛИ. Выполните операцию исключающего ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.  
  
 [x <<= ](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) — назначение со сдвигом влево. Сдвиньте значение `x` влево на `y` позиций, сохраните результат в `x` и возвратите новое значение.  
  
 [x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) — назначение со сдвигом вправо. Сдвиньте значение `x` вправо на `y` позиций, сохраните результат в `x` и возвратите новое значение.  
  
 [=>](../../../csharp/language-reference/operators/lambda-operator.md) — объявление лямбда-выражения.  
  
## <a name="arithmetic-overflow"></a>Переполнение при арифметической операции  
 Арифметические операторы ([+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md)) могут возвращать результаты, выходящие за пределы диапазона возможных значений для используемого числового типа. Подробнее см. в разделе, посвященном конкретному оператору, однако в общем случае применяются следующие правила.  
  
- Переполнение при целочисленных арифметических операциях либо вызывает исключение <xref:System.OverflowException> или отбрасывает старшие биты результата. Деление целого числа на ноль всегда вызывает исключение <xref:System.DivideByZeroException>.  

   Что именно произойдет при возникновении переполнения для целочисленного значения, зависит от контекста выполнения, который может быть [проверяемым или непроверяемым](../../../csharp/language-reference/keywords/checked-and-unchecked.md). В проверяемом контексте возникает исключение <xref:System.OverflowException>. В непроверяемом контексте старшие биты результата отбрасываются и выполнение продолжается. Таким образом, C# позволяет сделать выбор между обработкой и игнорированием переполнения. По умолчанию арифметические операции выполняются в *непроверяемом* контексте. 

   Кроме арифметических операторов, переполнение могут вызвать приведения целочисленного типа к другому целочисленному типу, например приведение [long](../../../csharp/language-reference/keywords/long.md) к [int](../../../csharp/language-reference/keywords/int.md). Для таких ситуаций также применяются проверяемый и непроверяемый контексты. Однако битовые операторы и операторы сдвига никогда не вызывают переполнение.  
   
-   Переполнение или деление на ноль при арифметических операциях с плавающей запятой никогда не вызывает исключение, так как типы с плавающей запятой — а поэтому и правила для представления бесконечности и значения NaN (не число) — основаны на стандарте IEEE 754.  
  
-   Переполнение при [десятичной](../../../csharp/language-reference/keywords/decimal.md) арифметической операции всегда вызывает исключение <xref:System.OverflowException>. Деление десятичного числа на ноль всегда вызывает исключение <xref:System.DivideByZeroException>.  
  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [C#](../../../csharp/index.md) [Перегружаемые операторы](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
