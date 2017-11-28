---
title: "Выражения в C#. Краткий обзор языка C#"
description: "Выражения, операнды и операторы являются стандартными блоками языка C#"
keywords: ".NET, c#, выражения, оператор, операнд"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 7b7e321e6554818924a8a2b68afa4c787807bcba
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="expressions"></a><span data-ttu-id="861d5-104">Выражения</span><span class="sxs-lookup"><span data-stu-id="861d5-104">Expressions</span></span>

<span data-ttu-id="861d5-105">*Выражения* создаются из *операндов* и *операторов*.</span><span class="sxs-lookup"><span data-stu-id="861d5-105">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="861d5-106">Операторы в выражении указывают, какие действия нужно применить к операндам.</span><span class="sxs-lookup"><span data-stu-id="861d5-106">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="861d5-107">Примеры операторов: `+`, `-`, `*`, `/` и `new`.</span><span class="sxs-lookup"><span data-stu-id="861d5-107">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="861d5-108">Операндами могут являться литералы, поля, локальные переменные, выражения и т. п.</span><span class="sxs-lookup"><span data-stu-id="861d5-108">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="861d5-109">Если выражение содержит несколько операторов, порядок вычисления этих операторов определяется их *приоритетом*.</span><span class="sxs-lookup"><span data-stu-id="861d5-109">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="861d5-110">Например, выражение `x + y * z` вычисляется как `x + (y * z)`, поскольку оператор `*` имеет более высокий приоритет, чем оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="861d5-110">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="861d5-111">Если операнд располагается между двумя операторами с одинаковым приоритетом, порядок их выполнения определяется *ассоциативностью* операторов.</span><span class="sxs-lookup"><span data-stu-id="861d5-111">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="861d5-112">Все бинарные операторы, за исключением операторов присваивания, имеют *левую ассоциативность*,то есть эти операции выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="861d5-112">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="861d5-113">Например, выражение `x + y + z` вычисляется как `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="861d5-113">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="861d5-114">Операторы присваивания и условный оператор (`?:`) являются *правоассоциативными*  то есть эти операции выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="861d5-114">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="861d5-115">Например, выражение `x = y = z` вычисляется как `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="861d5-115">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="861d5-116">Приоритет и ассоциативность операторов можно изменять, используя скобки.</span><span class="sxs-lookup"><span data-stu-id="861d5-116">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="861d5-117">Например, в выражении `x + y * z` сначала `y` умножается на `z`, а результат прибавляется к `x`, а в выражении `(x + y) * z` сначала суммируются `x` и `y`, а результат умножается на `z`.</span><span class="sxs-lookup"><span data-stu-id="861d5-117">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="861d5-118">Большинство операторов допускают *перегрузку*.</span><span class="sxs-lookup"><span data-stu-id="861d5-118">Most operators can be *overloaded*.</span></span> <span data-ttu-id="861d5-119">Перегрузка операторов позволяет создать пользовательскую реализацию оператора для таких операций, в которых один или оба операнда имеют определяемый пользователем тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="861d5-119">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="861d5-120">В следующей таблице перечислены операторы C# и категории операторов в порядке приоритета (от самого высокого до самого низкого).</span><span class="sxs-lookup"><span data-stu-id="861d5-120">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="861d5-121">Операторы в одной категории имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="861d5-121">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="861d5-122">В каждой категории приведен список выражений для этой категории с описанием каждого типа выражений.</span><span class="sxs-lookup"><span data-stu-id="861d5-122">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="861d5-123">Первичный</span><span class="sxs-lookup"><span data-stu-id="861d5-123">Primary</span></span>
    - <span data-ttu-id="861d5-124">`x.m`. Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="861d5-124">`x.m`: Member access</span></span>
    - <span data-ttu-id="861d5-125">`x(...)`. Вызов метода и делегата</span><span class="sxs-lookup"><span data-stu-id="861d5-125">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="861d5-126">`x[...]`. Доступ к массиву и индексатору</span><span class="sxs-lookup"><span data-stu-id="861d5-126">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="861d5-127">`x++`. Постфиксный инкремент</span><span class="sxs-lookup"><span data-stu-id="861d5-127">`x++`: Post-increment</span></span>
    - <span data-ttu-id="861d5-128">`x--`. Постфиксный декремент</span><span class="sxs-lookup"><span data-stu-id="861d5-128">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="861d5-129">`new T(...)`. Создание объекта и делегата</span><span class="sxs-lookup"><span data-stu-id="861d5-129">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="861d5-130">`new T(...){...}`. Создание объекта с инициализатором</span><span class="sxs-lookup"><span data-stu-id="861d5-130">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="861d5-131">`new {...}`. Анонимный инициализатор объекта</span><span class="sxs-lookup"><span data-stu-id="861d5-131">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="861d5-132">`new T[...]`. Создание массива</span><span class="sxs-lookup"><span data-stu-id="861d5-132">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="861d5-133">`typeof(T)`: Получение <xref:System.Type> для объекта `T`</span><span class="sxs-lookup"><span data-stu-id="861d5-133">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="861d5-134">`checked(x)`. Вычисление выражения в проверенном контексте</span><span class="sxs-lookup"><span data-stu-id="861d5-134">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="861d5-135">`unchecked(x)`. Вычисление выражения в непроверенном контексте</span><span class="sxs-lookup"><span data-stu-id="861d5-135">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="861d5-136">`default(T)`. Получение значения по умолчанию для типа `T`</span><span class="sxs-lookup"><span data-stu-id="861d5-136">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="861d5-137">`delegate {...}`. Анонимная функция (анонимный метод)</span><span class="sxs-lookup"><span data-stu-id="861d5-137">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="861d5-138">Унарный</span><span class="sxs-lookup"><span data-stu-id="861d5-138">Unary</span></span>
    - <span data-ttu-id="861d5-139">`+x`. Тождественность</span><span class="sxs-lookup"><span data-stu-id="861d5-139">`+x`: Identity</span></span>
    - <span data-ttu-id="861d5-140">`-x`. Отрицание</span><span class="sxs-lookup"><span data-stu-id="861d5-140">`-x`: Negation</span></span>
    - <span data-ttu-id="861d5-141">`!x`. Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="861d5-141">`!x`: Logical negation</span></span>
    - <span data-ttu-id="861d5-142">`~x`. Поразрядное отрицание</span><span class="sxs-lookup"><span data-stu-id="861d5-142">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="861d5-143">`++x`. Префиксный инкремент</span><span class="sxs-lookup"><span data-stu-id="861d5-143">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="861d5-144">`--x`. Префиксный декремент</span><span class="sxs-lookup"><span data-stu-id="861d5-144">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="861d5-145">`(T)x`. Явное преобразование `x` в тип `T`</span><span class="sxs-lookup"><span data-stu-id="861d5-145">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="861d5-146">`await x`: Асинхронное ожидание завершения `x`</span><span class="sxs-lookup"><span data-stu-id="861d5-146">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="861d5-147">Мультипликативный</span><span class="sxs-lookup"><span data-stu-id="861d5-147">Multiplicative</span></span>
    - <span data-ttu-id="861d5-148">`x * y`. Умножение</span><span class="sxs-lookup"><span data-stu-id="861d5-148">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="861d5-149">`x / y`. Деление</span><span class="sxs-lookup"><span data-stu-id="861d5-149">`x / y`: Division</span></span>
    - <span data-ttu-id="861d5-150">`x % y`. Остаток от деления</span><span class="sxs-lookup"><span data-stu-id="861d5-150">`x % y`: Remainder</span></span>
* <span data-ttu-id="861d5-151">Аддитивный</span><span class="sxs-lookup"><span data-stu-id="861d5-151">Additive</span></span>
    - <span data-ttu-id="861d5-152">`x + y`. Сложение, объединение строк, объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="861d5-152">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="861d5-153">`x – y`. Вычитание, удаление делегатов</span><span class="sxs-lookup"><span data-stu-id="861d5-153">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="861d5-154">Сдвиг</span><span class="sxs-lookup"><span data-stu-id="861d5-154">Shift</span></span>
    - <span data-ttu-id="861d5-155">`x << y`. Сдвиг влево</span><span class="sxs-lookup"><span data-stu-id="861d5-155">`x << y`: Shift left</span></span>
    - <span data-ttu-id="861d5-156">`x >> y`. Сдвиг вправо</span><span class="sxs-lookup"><span data-stu-id="861d5-156">`x >> y`: Shift right</span></span>
* <span data-ttu-id="861d5-157">Тестирования типа и относительные</span><span class="sxs-lookup"><span data-stu-id="861d5-157">Relational and type testing</span></span>
    - <span data-ttu-id="861d5-158">`x < y`. Меньше, чем</span><span class="sxs-lookup"><span data-stu-id="861d5-158">`x < y`: Less than</span></span>
    - <span data-ttu-id="861d5-159">`x > y`. Больше, чем</span><span class="sxs-lookup"><span data-stu-id="861d5-159">`x > y`: Greater than</span></span>
    - <span data-ttu-id="861d5-160">`x <= y`. Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="861d5-160">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="861d5-161">`x >= y`. Больше или равно</span><span class="sxs-lookup"><span data-stu-id="861d5-161">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="861d5-162">`x is T`: Возвращает `true`, если `x` является `T`, или `false` в противном случае</span><span class="sxs-lookup"><span data-stu-id="861d5-162">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="861d5-163">`x as T`: Возвращает `x` с типом `T`, или `null` если `x` не является `T`</span><span class="sxs-lookup"><span data-stu-id="861d5-163">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="861d5-164">Равенство</span><span class="sxs-lookup"><span data-stu-id="861d5-164">Equality</span></span>
    - <span data-ttu-id="861d5-165">`x == y`. Равенство</span><span class="sxs-lookup"><span data-stu-id="861d5-165">`x == y`: Equal</span></span>
    - <span data-ttu-id="861d5-166">`x != y`. Неравенство</span><span class="sxs-lookup"><span data-stu-id="861d5-166">`x != y`: Not equal</span></span>
* <span data-ttu-id="861d5-167">Логическое И</span><span class="sxs-lookup"><span data-stu-id="861d5-167">Logical AND</span></span>
    - <span data-ttu-id="861d5-168">`x & y`. Поразрядное И для операндов целочисленного типа, логическое И для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="861d5-168">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="861d5-169">Логическое исключающее ИЛИ</span><span class="sxs-lookup"><span data-stu-id="861d5-169">Logical XOR</span></span>
    - <span data-ttu-id="861d5-170">`x ^ y`. Поразрядное исключающее ИЛИ для операндов целочисленного типа, логическое исключающее ИЛИ для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="861d5-170">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="861d5-171">Логическое ИЛИ</span><span class="sxs-lookup"><span data-stu-id="861d5-171">Logical OR</span></span>
    - <span data-ttu-id="861d5-172">`x | y`. Поразрядное ИЛИ для операндов целочисленного типа, логическое ИЛИ для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="861d5-172">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="861d5-173">Условное И</span><span class="sxs-lookup"><span data-stu-id="861d5-173">Conditional AND</span></span>
    - <span data-ttu-id="861d5-174">`x && y`: Возвращает `y`, только если `x` не равно `false`</span><span class="sxs-lookup"><span data-stu-id="861d5-174">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="861d5-175">Условное ИЛИ</span><span class="sxs-lookup"><span data-stu-id="861d5-175">Conditional OR</span></span>
    - <span data-ttu-id="861d5-176">`x || y`: Возвращает `y`, только если `x` не равно `true`</span><span class="sxs-lookup"><span data-stu-id="861d5-176">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="861d5-177">Объединение со значением NULL</span><span class="sxs-lookup"><span data-stu-id="861d5-177">Null coalescing</span></span>
    - <span data-ttu-id="861d5-178">`x ?? y`: Возвращает значение `y`, если `x` имеет значение Null, или `x` в противном случае</span><span class="sxs-lookup"><span data-stu-id="861d5-178">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="861d5-179">Условие</span><span class="sxs-lookup"><span data-stu-id="861d5-179">Conditional</span></span>
    - <span data-ttu-id="861d5-180">`x ? y : z`: Возвращает `y`, если `x` имеет значение `true`, или `z`, если `x` имеет значение `false`</span><span class="sxs-lookup"><span data-stu-id="861d5-180">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="861d5-181">Присваивание или анонимная функция</span><span class="sxs-lookup"><span data-stu-id="861d5-181">Assignment or anonymous function</span></span>
    - <span data-ttu-id="861d5-182">`x = y`. Присваивание</span><span class="sxs-lookup"><span data-stu-id="861d5-182">`x = y`: Assignment</span></span>
    - <span data-ttu-id="861d5-183">`x op= y`. Составное присваивание, поддерживаются операторы</span><span class="sxs-lookup"><span data-stu-id="861d5-183">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="861d5-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="861d5-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="861d5-185">`(T x) => y`. Анонимная функция (лямбда-выражение)</span><span class="sxs-lookup"><span data-stu-id="861d5-185">`(T x) => y`: Anonymous function (lambda expression)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="861d5-186">[Назад](types-and-variables.md)
[Вперед](statements.md)</span><span class="sxs-lookup"><span data-stu-id="861d5-186">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
