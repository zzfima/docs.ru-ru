---
title: Выражения в C#. Краткий обзор языка C#
description: Выражения, операнды и операторы являются стандартными блоками языка C#
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480759"
---
# <a name="expressions"></a><span data-ttu-id="7c569-103">Выражения</span><span class="sxs-lookup"><span data-stu-id="7c569-103">Expressions</span></span>

<span data-ttu-id="7c569-104">*Выражения* создаются из *операндов* и *операторов*.</span><span class="sxs-lookup"><span data-stu-id="7c569-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="7c569-105">Операторы в выражении указывают, какие действия нужно применить к операндам.</span><span class="sxs-lookup"><span data-stu-id="7c569-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="7c569-106">Примеры операторов: `+`, `-`, `*`, `/` и `new`.</span><span class="sxs-lookup"><span data-stu-id="7c569-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="7c569-107">Операндами могут являться литералы, поля, локальные переменные, выражения и т. п.</span><span class="sxs-lookup"><span data-stu-id="7c569-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="7c569-108">Если выражение содержит несколько операторов, порядок вычисления этих операторов определяется их *приоритетом*.</span><span class="sxs-lookup"><span data-stu-id="7c569-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="7c569-109">Например, выражение `x + y * z` вычисляется как `x + (y * z)`, поскольку оператор `*` имеет более высокий приоритет, чем оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="7c569-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="7c569-110">Если операнд располагается между двумя операторами с одинаковым приоритетом, порядок их выполнения определяется *ассоциативностью* операторов.</span><span class="sxs-lookup"><span data-stu-id="7c569-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="7c569-111">Все бинарные операторы, за исключением операторов присваивания, имеют *левую ассоциативность*,то есть эти операции выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="7c569-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="7c569-112">Например, выражение `x + y + z` вычисляется как `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="7c569-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="7c569-113">Операторы присваивания и условный оператор (`?:`) являются *правоассоциативными* то есть эти операции выполняются справа налево.</span><span class="sxs-lookup"><span data-stu-id="7c569-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="7c569-114">Например, выражение `x = y = z` вычисляется как `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="7c569-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="7c569-115">Приоритет и ассоциативность операторов можно изменять, используя скобки.</span><span class="sxs-lookup"><span data-stu-id="7c569-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="7c569-116">Например, в выражении `x + y * z` сначала `y` умножается на `z`, а результат прибавляется к `x`, а в выражении `(x + y) * z` сначала суммируются `x` и `y`, а результат умножается на `z`.</span><span class="sxs-lookup"><span data-stu-id="7c569-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="7c569-117">Большинство операторов допускают *перегрузку*.</span><span class="sxs-lookup"><span data-stu-id="7c569-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="7c569-118">Перегрузка операторов позволяет создать пользовательскую реализацию оператора для таких операций, в которых один или оба операнда имеют определяемый пользователем тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7c569-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="7c569-119">В следующей таблице перечислены операторы C# и категории операторов в порядке приоритета (от самого высокого до самого низкого).</span><span class="sxs-lookup"><span data-stu-id="7c569-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="7c569-120">Операторы в одной категории имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="7c569-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="7c569-121">В каждой категории приведен список выражений для этой категории с описанием каждого типа выражений.</span><span class="sxs-lookup"><span data-stu-id="7c569-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="7c569-122">Первичный</span><span class="sxs-lookup"><span data-stu-id="7c569-122">Primary</span></span>
  - `x.m`<span data-ttu-id="7c569-123">: Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="7c569-123">: Member access</span></span>
  - `x(...)`<span data-ttu-id="7c569-124">: Вызов метода и делегата</span><span class="sxs-lookup"><span data-stu-id="7c569-124">: Method and delegate invocation</span></span>
  - `x[...]`<span data-ttu-id="7c569-125">: Доступ к массиву и индексатору</span><span class="sxs-lookup"><span data-stu-id="7c569-125">: Array and indexer access</span></span>
  - `x++`<span data-ttu-id="7c569-126">: Постфиксный инкремент</span><span class="sxs-lookup"><span data-stu-id="7c569-126">: Post-increment</span></span>
  - `x--`<span data-ttu-id="7c569-127">: Постфиксный декремент</span><span class="sxs-lookup"><span data-stu-id="7c569-127">: Post-decrement</span></span>
  - `new T(...)`<span data-ttu-id="7c569-128">: Создание объекта и делегата</span><span class="sxs-lookup"><span data-stu-id="7c569-128">: Object and delegate creation</span></span>
  - `new T(...){...}`<span data-ttu-id="7c569-129">: создание объекта с инициализатором</span><span class="sxs-lookup"><span data-stu-id="7c569-129">: Object creation with initializer</span></span>
  - `new {...}`<span data-ttu-id="7c569-130">:  анонимный инициализатор объекта</span><span class="sxs-lookup"><span data-stu-id="7c569-130">:  Anonymous object initializer</span></span>
  - `new T[...]`<span data-ttu-id="7c569-131">: создание массива</span><span class="sxs-lookup"><span data-stu-id="7c569-131">: Array creation</span></span>
  - `typeof(T)`<span data-ttu-id="7c569-132">: получение объекта <xref:System.Type> для</span><span class="sxs-lookup"><span data-stu-id="7c569-132">: Obtain <xref:System.Type> object for</span></span> `T`
  - `checked(x)`<span data-ttu-id="7c569-133">: Вычисление выражения в проверенном контексте</span><span class="sxs-lookup"><span data-stu-id="7c569-133">: Evaluate expression in checked context</span></span>
  - `unchecked(x)`<span data-ttu-id="7c569-134">: Вычисление выражения в непроверенном контексте</span><span class="sxs-lookup"><span data-stu-id="7c569-134">: Evaluate expression in unchecked context</span></span>
  - `default(T)`<span data-ttu-id="7c569-135">: получение значения по умолчанию для типа</span><span class="sxs-lookup"><span data-stu-id="7c569-135">: Obtain default value of type</span></span> `T`
  - `delegate {...}`<span data-ttu-id="7c569-136">: Анонимная функция (анонимный метод)</span><span class="sxs-lookup"><span data-stu-id="7c569-136">: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="7c569-137">Унарный</span><span class="sxs-lookup"><span data-stu-id="7c569-137">Unary</span></span>
  - `+x`<span data-ttu-id="7c569-138">: идентификации</span><span class="sxs-lookup"><span data-stu-id="7c569-138">: Identity</span></span>
  - `-x`<span data-ttu-id="7c569-139">: Отрицание</span><span class="sxs-lookup"><span data-stu-id="7c569-139">: Negation</span></span>
  - `!x`<span data-ttu-id="7c569-140">: Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="7c569-140">: Logical negation</span></span>
  - `~x`<span data-ttu-id="7c569-141">: Поразрядное отрицание</span><span class="sxs-lookup"><span data-stu-id="7c569-141">: Bitwise negation</span></span>
  - `++x`<span data-ttu-id="7c569-142">: Префиксный инкремент</span><span class="sxs-lookup"><span data-stu-id="7c569-142">: Pre-increment</span></span>
  - `--x`<span data-ttu-id="7c569-143">: Префиксный декремент</span><span class="sxs-lookup"><span data-stu-id="7c569-143">: Pre-decrement</span></span>
  - `(T)x`<span data-ttu-id="7c569-144">: явное преобразование `x` в тип</span><span class="sxs-lookup"><span data-stu-id="7c569-144">: Explicitly convert `x` to type</span></span> `T`
  - `await x`<span data-ttu-id="7c569-145">: асинхронное ожидание завершения `x`</span><span class="sxs-lookup"><span data-stu-id="7c569-145">: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="7c569-146">Мультипликативный</span><span class="sxs-lookup"><span data-stu-id="7c569-146">Multiplicative</span></span>
  - `x * y`<span data-ttu-id="7c569-147">: Умножение</span><span class="sxs-lookup"><span data-stu-id="7c569-147">: Multiplication</span></span>
  - `x / y`<span data-ttu-id="7c569-148">: Деление</span><span class="sxs-lookup"><span data-stu-id="7c569-148">: Division</span></span>
  - `x % y`<span data-ttu-id="7c569-149">: Остаток</span><span class="sxs-lookup"><span data-stu-id="7c569-149">: Remainder</span></span>
* <span data-ttu-id="7c569-150">Аддитивный</span><span class="sxs-lookup"><span data-stu-id="7c569-150">Additive</span></span>
  - `x + y`<span data-ttu-id="7c569-151">: Сложение, объединение строк, объединение делегатов</span><span class="sxs-lookup"><span data-stu-id="7c569-151">: Addition, string concatenation, delegate combination</span></span>
  - `x – y`<span data-ttu-id="7c569-152">: Вычитание, удаление делегатов</span><span class="sxs-lookup"><span data-stu-id="7c569-152">: Subtraction, delegate removal</span></span>
* <span data-ttu-id="7c569-153">Сдвиг</span><span class="sxs-lookup"><span data-stu-id="7c569-153">Shift</span></span>
  - `x << y`<span data-ttu-id="7c569-154">: Сдвиг влево</span><span class="sxs-lookup"><span data-stu-id="7c569-154">: Shift left</span></span>
  - `x >> y`<span data-ttu-id="7c569-155">: Сдвиг вправо</span><span class="sxs-lookup"><span data-stu-id="7c569-155">: Shift right</span></span>
* <span data-ttu-id="7c569-156">Тестирования типа и относительные</span><span class="sxs-lookup"><span data-stu-id="7c569-156">Relational and type testing</span></span>
  - `x < y`<span data-ttu-id="7c569-157">: Меньше</span><span class="sxs-lookup"><span data-stu-id="7c569-157">: Less than</span></span>
  - `x > y`<span data-ttu-id="7c569-158">: Больше</span><span class="sxs-lookup"><span data-stu-id="7c569-158">: Greater than</span></span>
  - `x <= y`<span data-ttu-id="7c569-159">: Меньше или равно</span><span class="sxs-lookup"><span data-stu-id="7c569-159">: Less than or equal</span></span>
  - `x >= y`<span data-ttu-id="7c569-160">: Больше или равно</span><span class="sxs-lookup"><span data-stu-id="7c569-160">: Greater than or equal</span></span>
  - `x is T`<span data-ttu-id="7c569-161">: возвращает `true`, если `x` является `T`, или `false` в противном случае</span><span class="sxs-lookup"><span data-stu-id="7c569-161">: Return `true` if `x` is a `T`, `false` otherwise</span></span>
  - `x as T`<span data-ttu-id="7c569-162">: возвращает `x` с типом `T` или `null`, если `x` не является</span><span class="sxs-lookup"><span data-stu-id="7c569-162">: Return `x` typed as `T`, or `null` if `x` is not a</span></span> `T`
* <span data-ttu-id="7c569-163">Равенство</span><span class="sxs-lookup"><span data-stu-id="7c569-163">Equality</span></span>
  - `x == y`<span data-ttu-id="7c569-164">: Равно</span><span class="sxs-lookup"><span data-stu-id="7c569-164">: Equal</span></span>
  - `x != y`<span data-ttu-id="7c569-165">: Не равно</span><span class="sxs-lookup"><span data-stu-id="7c569-165">: Not equal</span></span>
* <span data-ttu-id="7c569-166">Логическое И</span><span class="sxs-lookup"><span data-stu-id="7c569-166">Logical AND</span></span>
  - `x & y`<span data-ttu-id="7c569-167">: поразрядное логическое И для операндов целочисленного типа, логическое И для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="7c569-167">: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="7c569-168">Логическое исключающее ИЛИ</span><span class="sxs-lookup"><span data-stu-id="7c569-168">Logical XOR</span></span>
  - `x ^ y`<span data-ttu-id="7c569-169">: Поразрядное исключающее ИЛИ для операндов целочисленного типа, логическое исключающее ИЛИ для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="7c569-169">: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="7c569-170">Логическое ИЛИ</span><span class="sxs-lookup"><span data-stu-id="7c569-170">Logical OR</span></span>
  - `x | y`<span data-ttu-id="7c569-171">: Поразрядное ИЛИ для операндов целочисленного типа, логическое ИЛИ для операндов логического типа</span><span class="sxs-lookup"><span data-stu-id="7c569-171">: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="7c569-172">Условное И</span><span class="sxs-lookup"><span data-stu-id="7c569-172">Conditional AND</span></span>
  - `x && y`<span data-ttu-id="7c569-173">: возвращает `y`, только если `x` не равно</span><span class="sxs-lookup"><span data-stu-id="7c569-173">: Evaluates `y` only if `x` is not</span></span> `false`
* <span data-ttu-id="7c569-174">Условное ИЛИ</span><span class="sxs-lookup"><span data-stu-id="7c569-174">Conditional OR</span></span>
  - `x || y`<span data-ttu-id="7c569-175">: возвращает `y`, только если `x` не равно</span><span class="sxs-lookup"><span data-stu-id="7c569-175">: Evaluates `y` only if `x` is not</span></span> `true`
* <span data-ttu-id="7c569-176">Объединение со значением NULL</span><span class="sxs-lookup"><span data-stu-id="7c569-176">Null coalescing</span></span>
  - `x ?? y`<span data-ttu-id="7c569-177">: возвращает значение `y`, если `x` имеет значение NULL, или `x` в противном случае</span><span class="sxs-lookup"><span data-stu-id="7c569-177">: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="7c569-178">Условие</span><span class="sxs-lookup"><span data-stu-id="7c569-178">Conditional</span></span>
  - `x ? y : z`<span data-ttu-id="7c569-179">: возвращает `y`, если `x` имеет значение `true`, или `z`, если `x` имеет значение</span><span class="sxs-lookup"><span data-stu-id="7c569-179">: Evaluates `y` if `x` is `true`, `z` if `x` is</span></span> `false`
* <span data-ttu-id="7c569-180">Присваивание или анонимная функция</span><span class="sxs-lookup"><span data-stu-id="7c569-180">Assignment or anonymous function</span></span>
  - `x = y`<span data-ttu-id="7c569-181">: Назначение</span><span class="sxs-lookup"><span data-stu-id="7c569-181">: Assignment</span></span>
  - `x op= y`<span data-ttu-id="7c569-182">: составное присваивание, поддерживаются операторы</span><span class="sxs-lookup"><span data-stu-id="7c569-182">: Compound assignment; supported operators are</span></span>
    - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
  - `(T x) => y`<span data-ttu-id="7c569-183">: Анонимная функция (лямбда-выражение)</span><span class="sxs-lookup"><span data-stu-id="7c569-183">: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="7c569-184">[Назад](types-and-variables.md)
> [Вперед](statements.md)</span><span class="sxs-lookup"><span data-stu-id="7c569-184">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
