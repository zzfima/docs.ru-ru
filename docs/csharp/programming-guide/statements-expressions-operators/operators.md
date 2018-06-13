---
title: Операторы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 76371985e340945793310247ec48d9b0cb747aed
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457934"
---
# <a name="operators-c-programming-guide"></a>Операторы (Руководство по программированию на C#)
В языке C# *оператор* — это элемент программы, который применяется для одного или нескольких *операндов* в выражении или инструкции. Операторы, в которых используется один операнд, например оператор инкремента (`++`) или `new`, называются *унарными* . Операторы, в которых используются два операнда, например арифметические операторы (`+`,`-`,`*`,`/`), называются *бинарными* . Для одного оператора — условного (`?:`) — используются три операнда, и такой оператор является единственным троичным оператором в C#.  
  
 Следующая строка кода C# содержит один унарный оператор и еще один операнд. Оператор инкремента `++`изменяет значение операнда `y`.  
  
 [!code-csharp[csProgGuideStatements#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/operators_1.cs)]  
  
 Следующая строка кода C# содержит два бинарных оператора с двумя операндами в каждом. Оператор присваивания `=`содержит в качестве операндов целочисленную переменную `y` и выражение `2 + 3` . Выражение `2 + 3` состоит из оператора сложения и двух операндов — `2` и `3`.  
  
 [!code-csharp[csProgGuideStatements#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/operators_2.cs)]  
  
## <a name="operators-evaluation-and-operator-precedence"></a>Операторы, вычисление выражений и приоритет операторов  
 Операнд может быть допустимым выражением, представляющим собой код любой длины, а также может содержать любое число вложенных выражений. В выражении, содержащем несколько операторов, порядок применения операторов определяется *приоритетом операторов*, *ассоциативностью*и скобками.  
  
 Каждый оператор имеет определенный приоритет. В выражении, содержащем несколько операторов с разными уровнями приоритета, порядок вычисления операторов определяется их приоритетом. Например, в следующем операторе переменной `n1`присваивается значение 3.  
  
 `n1 = 11 - 2 * 4;`  
  
 Сначала выполняется умножение, так как оно имеет приоритет над вычитанием.  
  
 В следующей таблице операторы разделены на категории на основе типа выполняемых операций. Категории указаны в порядке приоритета.  
  
 **Основные операторы**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|x[.](../../../csharp/language-reference/operators/member-access-operator.md)y<br /><br /> x?.y|Доступ к членам<br /><br /> Условный доступ к членам|  
|f[(x)](../../../csharp/language-reference/operators/invocation-operator.md)|Вызов метода и делегата|  
|a[&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md)<br /><br /> a?[x]|Доступ к массиву и индексатору<br /><br /> Условный доступ к массиву и индексатору|  
|x[++](../../../csharp/language-reference/operators/increment-operator.md)|Постфиксный инкремент|  
|x[--](../../../csharp/language-reference/operators/decrement-operator.md)|Постфиксный декремент|  
|[new](../../../csharp/language-reference/keywords/new-operator.md) T(...)|Создание объекта и делегата|  
|`new` T(...){...}|Создание объекта с инициализатором. См. раздел [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).|  
|`new` {...}|Анонимный инициализатор объекта. См. раздел [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).|  
|`new` T[...]|Создание массива. См. раздел [Массивы](../../../csharp/programming-guide/arrays/index.md).|  
|[typeof](../../../csharp/language-reference/keywords/typeof.md)(T)|Получение объекта System.Type для T|  
|[checked](../../../csharp/language-reference/keywords/checked.md)(x)|Вычисление выражения в проверенном контексте|  
|[unchecked](../../../csharp/language-reference/keywords/unchecked.md)(x)|Вычисление выражения в непроверенном контексте|  
|[default](../../../csharp/language-reference/keywords/default.md) (T)|Получение значения по умолчанию для типа T|  
|[delegate](../../../csharp/language-reference/keywords/delegate.md) {}|Анонимная функция (анонимный метод)|  
  
 **Унарные операторы**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|[+](../../../csharp/language-reference/operators/addition-operator.md)x|идентификации|  
|[-](../../../csharp/language-reference/operators/subtraction-operator.md)x|Отрицание|  
|[\!](../../../csharp/language-reference/operators/logical-negation-operator.md)x|Логическое отрицание|  
|[~](../../../csharp/language-reference/operators/bitwise-complement-operator.md)x|Поразрядное отрицание|  
|[++](../../../csharp/language-reference/operators/increment-operator.md)x|Префиксный инкремент|  
|[--](../../../csharp/language-reference/operators/decrement-operator.md)x|Префиксный декремент|  
|[(T)](../../../csharp/language-reference/operators/invocation-operator.md)x|Явное преобразование x в тип T|  
  
 **Мультипликативные операторы**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|[*](../../../csharp/language-reference/operators/multiplication-operator.md)|Умножение|  
|[/](../../../csharp/language-reference/operators/division-operator.md)|Деление|  
|[%](../../../csharp/language-reference/operators/modulus-operator.md)|Остаток|  
  
 **Аддитивные операторы**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|x [+](../../../csharp/language-reference/operators/addition-operator.md) y|Сложение, объединение строк, объединение делегатов|  
|x [-](../../../csharp/language-reference/operators/subtraction-operator.md) y|Вычитание, удаление делегатов|  
  
 **Операторы сдвига**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|x [<\<](../../../csharp/language-reference/operators/left-shift-operator.md) y|Сдвиг влево|  
|x [>>](../../../csharp/language-reference/operators/right-shift-operator.md) y|Сдвиг вправо|  
  
 **Относительные операторы и операторы типов**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|x [\<](../../../csharp/language-reference/operators/less-than-operator.md) y|Меньше|  
|x [>](../../../csharp/language-reference/operators/greater-than-operator.md) y|Больше|  
|x [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) y|Меньше или равно|  
|x [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) y|Больше или равно|  
|x [is](../../../csharp/language-reference/keywords/is.md) T|Возвращает значение true, если x относится к типу T, в противном случае возвращает значение false|  
|x [as](../../../csharp/language-reference/keywords/as.md) T|Возвращает x типа T или значение NULL, если x не относится к типу T|  
  
 **Операторы равенства**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|x [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) y|Равно|  
|x [!=](../../../csharp/language-reference/operators/not-equal-operator.md) y|Не равно|  
  
 **Логические, условные операторы и NULL-операторы**  
  
|Категория|Выражение|Описание:|  
|--------------|----------------|-----------------|  
|Логическое И|x [&](../../../csharp/language-reference/operators/and-operator.md) y|Поразрядное И для операндов целочисленного типа, логическое И для операндов логического типа|  
|Логическое исключающее ИЛИ|x [^](../../../csharp/language-reference/operators/xor-operator.md) y|Поразрядное исключающее ИЛИ для операндов целочисленного типа, логическое исключающее ИЛИ для операндов логического типа|  
|Логическое ИЛИ|x [&#124;](../../../csharp/language-reference/operators/or-operator.md) y|Поразрядное ИЛИ для операндов целочисленного типа, логическое ИЛИ для операндов логического типа|  
|Условное И|x [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y|Равно y, только если x имеет значение true|  
|Условное ИЛИ|x [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) y|Равно y, только если x имеет значение false|  
|Объединение со значением NULL|x [??](../../../csharp/language-reference/operators/null-coalescing-operator.md) Y|Равно y, если x имеет значение NULL, в противном случае равно x|  
|Условие|x [?](../../../csharp/language-reference/operators/conditional-operator.md) y : z|Равно y, если x имеет значение true, и z, если x имеет значение false|  
  
 **Операторы присваивания и анонимные операторы**  
  
|Выражение|Описание:|  
|----------------|-----------------|  
|[=](../../../csharp/language-reference/operators/assignment-operator.md)|Назначение|  
|x op= y|Составное присваивание. Поддерживает следующие операторы: [+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [!=](../../../csharp/language-reference/operators/not-equal-operator.md), [<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|  
|(T x) [=>](../../../csharp/language-reference/operators/lambda-operator.md) y|Анонимная функция (лямбда-выражение)|  
  
## <a name="associativity"></a>Ассоциативность  
 Когда выражение содержит два или более операторов с одинаковым приоритетом, они вычисляются на основе ассоциативности. Операторы с левой ассоциативностью вычисляются слева направо. Например, выражение `x * y / z` вычисляется как `(x * y) / z`. Операторы с правой ассоциативностью вычисляются справа налево. Например, оператор присваивания имеет правую ассоциативность. Если бы это было не так, следующий код вызвал бы ошибку.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 Другим примером оператора с правой ассоциативностью является троичный оператор ([?:](../../../csharp/language-reference/operators/conditional-operator.md)). Большинство двоичных операторов имеют левую ассоциативность.  
  
 Независимо от того, какую ассоциативность (левую или правую) имеют операторы в выражении, сначала вычисляются операнды каждого выражения — слева направо. В следующих примерах иллюстрируется порядок вычисления операторов и операндов.  
  
|Оператор|Порядок вычислений|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>Добавление скобок  
 Порядок, определяемый приоритетом и ассоциативностью операторов, можно изменить с помощью скобок. Например, выражение `2 + 3 * 2` в обычном случае будет иметь значение 8, поскольку операторы умножения выполняются раньше операторов сложения. Однако если выражение записано в форме `(2 + 3) * 2`, сложение выполняется перед умножением и в результате получается 10. В следующих примерах иллюстрируется порядок вычисления выражений в скобках. Как и в предыдущих примерах, перед применением оператора вычисляются операнды.  
  
|Оператор|Порядок вычислений|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>Перегрузка операторов  
 Поведение операторов для пользовательских классов и структур можно изменить. Такой процесс называется *перегрузкой операторов*. Дополнительные сведения см. в разделе [Перегружаемые операторы](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения см. в разделах [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md) и [Операторы C#](../../../csharp/language-reference/operators/index.md).  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Инструкции, выражения и операторы](../../../csharp/programming-guide/statements-expressions-operators/index.md)
