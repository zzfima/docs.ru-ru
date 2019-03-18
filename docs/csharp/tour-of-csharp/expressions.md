---
title: Выражения в C#. Краткий обзор языка C#
description: Выражения, операнды и операторы являются стандартными блоками языка C#
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 7a7f65eb7ba3da3f9630bbcb92d8578d60d2095d
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846601"
---
# <a name="expressions"></a><span data-ttu-id="a1879-103">Выражения</span><span class="sxs-lookup"><span data-stu-id="a1879-103">Expressions</span></span>

<span data-ttu-id="a1879-104">*Выражения* создаются из *операндов* и *операторов*.</span><span class="sxs-lookup"><span data-stu-id="a1879-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="a1879-105">Операторы в выражении указывают, какие действия нужно применить к операндам.</span><span class="sxs-lookup"><span data-stu-id="a1879-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="a1879-106">Примеры операторов: `+`, `-`, `*`, `/` и `new`.</span><span class="sxs-lookup"><span data-stu-id="a1879-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="a1879-107">Операндами могут являться литералы, поля, локальные переменные, выражения и т. п.</span><span class="sxs-lookup"><span data-stu-id="a1879-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="a1879-108">Если выражение содержит несколько операторов, порядок вычисления этих операторов определяется их *приоритетом*.</span><span class="sxs-lookup"><span data-stu-id="a1879-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="a1879-109">Например, выражение `x + y * z` вычисляется как `x + (y * z)`, поскольку оператор `*` имеет более высокий приоритет, чем оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="a1879-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="a1879-110">Если операнд располагается между двумя операторами с одинаковым приоритетом, порядок их выполнения определяется *ассоциативностью* операторов.</span><span class="sxs-lookup"><span data-stu-id="a1879-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="a1879-111">Все бинарные операторы, за исключением операторов присваивания, имеют *левую ассоциативность*,то есть эти операции выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="a1879-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="a1879-112">Например, выражение `x + y + z` вычисляется как `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="a1879-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="a1879-113">Операторы присваивания и условный оператор (`?:`) являются *правоассоциативными* то есть эти операции выполняются справа налево.</span><span class="sxs-lookup"><span data-stu-id="a1879-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="a1879-114">Например, выражение `x = y = z` вычисляется как `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="a1879-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="a1879-115">Приоритет и ассоциативность операторов можно изменять, используя скобки.</span><span class="sxs-lookup"><span data-stu-id="a1879-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="a1879-116">Например, в выражении `x + y * z` сначала `y` умножается на `z`, а результат прибавляется к `x`, а в выражении `(x + y) * z` сначала суммируются `x` и `y`, а результат умножается на `z`.</span><span class="sxs-lookup"><span data-stu-id="a1879-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="a1879-117">Большинство операторов допускают *перегрузку*.</span><span class="sxs-lookup"><span data-stu-id="a1879-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="a1879-118">Перегрузка операторов позволяет создать пользовательскую реализацию оператора для таких операций, в которых один или оба операнда имеют определяемый пользователем тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="a1879-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="a1879-119">В следующей таблице перечислены операторы C# и категории операторов в порядке приоритета (от самого высокого до самого низкого).</span><span class="sxs-lookup"><span data-stu-id="a1879-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="a1879-120">Операторы в одной категории имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="a1879-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="a1879-121">В каждой категории приведен список выражений для этой категории с описанием каждого типа выражений.</span><span class="sxs-lookup"><span data-stu-id="a1879-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="a1879-122">Первичный</span><span class="sxs-lookup"><span data-stu-id="a1879-122">Primary</span></span>
    - <span data-ttu-id="a1879-123">`x.m`: Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="a1879-123">`x.m`: Member access</span></span>
    - <span data-ttu-id="a1879-124">`x(...)`: Вызов метода и делегата</span><span class="sxs-lookup"><span data-stu-id="a1879-124">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="a1879-125">`x[...]`: Доступ к массиву и индексатору</span><span class="sxs-lookup"><span data-stu-id="a1879-125">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="a1879-126">`x++`: Постфиксный инкремент</span><span class="sxs-lookup"><span data-stu-id="a1879-126">`x++`: Post-increment</span></span>
    - <span data-ttu-id="a1879-127">`x--`: Постфиксный декремент</span><span class="sxs-lookup"><span data-stu-id="a1879-127">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="a1879-128">`new T(...)`: Создание объекта и делегата</span><span class="sxs-lookup"><span data-stu-id="a1879-128">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="a1879-129">`new T(...){...}`: создание объекта с инициализатором</span><span class="sxs-lookup"><span data-stu-id="a1879-129">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="a1879-130">`new {...}`:  анонимный инициализатор объекта</span><span class="sxs-lookup"><span data-stu-id="a1879-130">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="a1879-131">`new T[...]`: создание массива</span><span class="sxs-lookup"><span data-stu-id="a1879-131">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="a1879-132">`typeof(T)`: получение объекта <xref:System.Type> для `T`</span><span class="sxs-lookup"><span data-stu-id="a1879-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="a1879-133">`checked(x)`: Вычисление выражения в проверенном контексте</span><span class="sxs-lookup"><span data-stu-id="a1879-133">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="a1879-134">`unchecked(x)`: Вычисление выражения в непроверенном контексте</span><span class="sxs-lookup"><span data-stu-id="a1879-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="a1879-135">`default(T)`: получение значения по умолчанию для типа `T`</span><span class="sxs-lookup"><span data-stu-id="a1879-135">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="a1879-136">`delegate {...}`: Анонимная функция (анонимный метод)</span><span class="sxs-lookup"><span data-stu-id="a1879-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="a1879-137">Унарный</span><span class="sxs-lookup"><span data-stu-id="a1879-137">Unary</span></span>
    - <span data-ttu-id="a1879-138">`+x`: идентификации</span><span class="sxs-lookup"><span data-stu-id="a1879-138">`+x`: Identity</span></span>
    - <span data-ttu-id="a1879-139">`-x`: Отрицание</span><span class="sxs-lookup"><span data-stu-id="a1879-139">`-x`: Negation</span></span>
    - <span data-ttu-id="a1879-140">`!x`: Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="a1879-140">`!x`: Logical negation</span></span>
    - <span data-ttu-id="a1879-141">`~x`: Поразрядное отрицание</span><span class="sxs-lookup"><span data-stu-id="a1879-141">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="a1879-142">`++x`: Префиксный инкремент</span><span class="sxs-lookup"><span data-stu-id="a1879-142">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="a1879-143">`--x`: Префиксный декремент</span><span class="sxs-lookup"><span data-stu-id="a1879-143">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="a1879-144">`(T)x`: явное преобразование `x` в тип `T`</span><span class="sxs-lookup"><span data-stu-id="a1879-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="a1879-145">`await x`: асинхронное ожидание завершения `x`</span><span class="sxs-lookup"><span data-stu-id="a1879-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="a1879-146">Мультипликативный</span><span class="sxs-lookup"><span data-stu-id="a1879-146">Multiplicative</span></span>
    - <span data-ttu-id="a1879-147">`x * y`: Умножение</span><span class="sxs-lookup"><span data-stu-id="a1879-147">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="a1879-148">`x / y`: Деление</span><span class="sxs-lookup"><span data-stu-id="a1879-148">`x / y`: Division</span></span>
    - <span data-ttu-id="a1879-149">`x % y`: Остаток</span><span class="sxs-lookup"><span data-stu-id="a1879-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="a1879-150">Аддитивный</span><span class="sxs-lookup"><span data-stu-id="a1879-150">Additive</span></span>
    - <span data-ttu-id="a1879-151">`x + y`: Сложение, объединение строк, объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="a1879-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="a1879-152">`x – y`: Вычитание, удаление делегатов</span><span class="sxs-lookup"><span data-stu-id="a1879-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="a1879-153">Сдвиг</span><span class="sxs-lookup"><span data-stu-id="a1879-153">Shift</span></span>
    - <span data-ttu-id="a1879-154">`x << y`: Сдвиг влево</span><span class="sxs-lookup"><span data-stu-id="a1879-154">`x << y`: Shift left</span></span>
    - <span data-ttu-id="a1879-155">`x >> y`: Сдвиг вправо</span><span class="sxs-lookup"><span data-stu-id="a1879-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="a1879-156">Тестирования типа и относительные</span><span class="sxs-lookup"><span data-stu-id="a1879-156">Relational and type testing</span></span>
    - <span data-ttu-id="a1879-157">`x < y`: Меньше</span><span class="sxs-lookup"><span data-stu-id="a1879-157">`x < y`: Less than</span></span>
    - <span data-ttu-id="a1879-158">`x > y`: Больше</span><span class="sxs-lookup"><span data-stu-id="a1879-158">`x > y`: Greater than</span></span>
    - <span data-ttu-id="a1879-159">`x <= y`: Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="a1879-159">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="a1879-160">`x >= y`: Больше или равно</span><span class="sxs-lookup"><span data-stu-id="a1879-160">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="a1879-161">`x is T`: возвращает `true`, если `x` является `T`, или `false` в противном случае</span><span class="sxs-lookup"><span data-stu-id="a1879-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="a1879-162">`x as T`: возвращает `x` с типом `T` или `null`, если `x` не является `T`</span><span class="sxs-lookup"><span data-stu-id="a1879-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="a1879-163">Равенство</span><span class="sxs-lookup"><span data-stu-id="a1879-163">Equality</span></span>
    - <span data-ttu-id="a1879-164">`x == y`: Равно</span><span class="sxs-lookup"><span data-stu-id="a1879-164">`x == y`: Equal</span></span>
    - <span data-ttu-id="a1879-165">`x != y`: Не равно</span><span class="sxs-lookup"><span data-stu-id="a1879-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="a1879-166">Логическое И</span><span class="sxs-lookup"><span data-stu-id="a1879-166">Logical AND</span></span>
    - <span data-ttu-id="a1879-167">`x & y`: поразрядное логическое И для операндов целочисленного типа, логическое И для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="a1879-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="a1879-168">Логическое исключающее ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a1879-168">Logical XOR</span></span>
    - <span data-ttu-id="a1879-169">`x ^ y`: Поразрядное исключающее ИЛИ для операндов целочисленного типа, логическое исключающее ИЛИ для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="a1879-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="a1879-170">Логическое ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a1879-170">Logical OR</span></span>
    - <span data-ttu-id="a1879-171">`x | y`: Поразрядное ИЛИ для операндов целочисленного типа, логическое ИЛИ для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="a1879-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="a1879-172">Условное И</span><span class="sxs-lookup"><span data-stu-id="a1879-172">Conditional AND</span></span>
    - <span data-ttu-id="a1879-173">`x && y`: возвращает `y`, только если `x` не равно `false`</span><span class="sxs-lookup"><span data-stu-id="a1879-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="a1879-174">Условное ИЛИ</span><span class="sxs-lookup"><span data-stu-id="a1879-174">Conditional OR</span></span>
    - <span data-ttu-id="a1879-175">`x || y`: возвращает `y`, только если `x` не равно `true`</span><span class="sxs-lookup"><span data-stu-id="a1879-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="a1879-176">Объединение со значением NULL</span><span class="sxs-lookup"><span data-stu-id="a1879-176">Null coalescing</span></span>
    - <span data-ttu-id="a1879-177">`x ?? y`: возвращает значение `y`, если `x` имеет значение NULL, или `x` в противном случае</span><span class="sxs-lookup"><span data-stu-id="a1879-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="a1879-178">Условие</span><span class="sxs-lookup"><span data-stu-id="a1879-178">Conditional</span></span>
    - <span data-ttu-id="a1879-179">`x ? y : z`: возвращает `y`, если `x` имеет значение `true`, или `z`, если `x` имеет значение `false`</span><span class="sxs-lookup"><span data-stu-id="a1879-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="a1879-180">Присваивание или анонимная функция</span><span class="sxs-lookup"><span data-stu-id="a1879-180">Assignment or anonymous function</span></span>
    - <span data-ttu-id="a1879-181">`x = y`: Назначение</span><span class="sxs-lookup"><span data-stu-id="a1879-181">`x = y`: Assignment</span></span>
    - <span data-ttu-id="a1879-182">`x op= y`: составное присваивание, поддерживаются операторы</span><span class="sxs-lookup"><span data-stu-id="a1879-182">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="a1879-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="a1879-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="a1879-184">`(T x) => y`: Анонимная функция (лямбда-выражение)</span><span class="sxs-lookup"><span data-stu-id="a1879-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="a1879-185">[Назад](types-and-variables.md)
> [Вперед](statements.md)</span><span class="sxs-lookup"><span data-stu-id="a1879-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
