---
title: Привязки let
description: Узнайте, как использовать F# привязку let, которая связывает идентификатор со значением или функцией.
ms.date: 05/16/2016
ms.openlocfilehash: 654631c7d1c48d8737e6098c98efee54cfdd91be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630635"
---
# <a name="let-bindings"></a><span data-ttu-id="f1abc-103">Привязки let</span><span class="sxs-lookup"><span data-stu-id="f1abc-103">let Bindings</span></span>

<span data-ttu-id="f1abc-104">*Привязка* связывает идентификатор со значением или функцией.</span><span class="sxs-lookup"><span data-stu-id="f1abc-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="f1abc-105">Используйте `let` ключевое слово для привязки имени к значению или функции.</span><span class="sxs-lookup"><span data-stu-id="f1abc-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1abc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1abc-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="f1abc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1abc-107">Remarks</span></span>

<span data-ttu-id="f1abc-108">`let` Ключевое слово используется в выражениях привязки для определения значений или значений функций для одного или нескольких имен.</span><span class="sxs-lookup"><span data-stu-id="f1abc-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="f1abc-109">Простейшая форма `let` выражения привязывает имя к простому значению, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f1abc-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="f1abc-110">Если выражение отделяется от идентификатора с помощью новой строки, необходимо задать отступ для каждой строки выражения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f1abc-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="f1abc-111">Вместо просто имени можно указать шаблон, содержащий имена, например кортеж, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f1abc-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="f1abc-112">*Выражение body* — это выражение, в котором используются имена.</span><span class="sxs-lookup"><span data-stu-id="f1abc-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="f1abc-113">Выражение тела отображается в отдельной строке с отступом до первого символа в `let` ключевом слове:</span><span class="sxs-lookup"><span data-stu-id="f1abc-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="f1abc-114">`let` Привязка может отображаться на уровне модуля, в определении типа класса или в локальных областях, например в определении функции.</span><span class="sxs-lookup"><span data-stu-id="f1abc-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="f1abc-115">Для `let` привязки на верхнем уровне модуля или в типе класса не требуется выражение тела, но на других уровнях области требуется выражение тела.</span><span class="sxs-lookup"><span data-stu-id="f1abc-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="f1abc-116">Привязанные имена можно использовать после точки определения, но не в любой точке перед `let` отображением привязки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f1abc-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="f1abc-117">Привязки функций</span><span class="sxs-lookup"><span data-stu-id="f1abc-117">Function Bindings</span></span>

<span data-ttu-id="f1abc-118">Привязки функций следуют правилам для привязок значений, за исключением того, что привязки функций включают имя функции и параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f1abc-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="f1abc-119">Как правило, параметры — это шаблоны, такие как шаблон кортежа:</span><span class="sxs-lookup"><span data-stu-id="f1abc-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="f1abc-120">Выражение `let` привязки принимает значение последнего выражения.</span><span class="sxs-lookup"><span data-stu-id="f1abc-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="f1abc-121">Таким образом, в следующем примере кода значение `result` вычисляется из `100 * function3 (1, 2)` `300`, результатом вычисления которого является.</span><span class="sxs-lookup"><span data-stu-id="f1abc-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="f1abc-122">См. дополнительные сведения о [функциях](index.md).</span><span class="sxs-lookup"><span data-stu-id="f1abc-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="f1abc-123">Аннотации типов</span><span class="sxs-lookup"><span data-stu-id="f1abc-123">Type Annotations</span></span>

<span data-ttu-id="f1abc-124">Можно указать типы для параметров, добавив двоеточие (:) , за которым следует имя типа, заключенное в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="f1abc-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="f1abc-125">Можно также указать тип возвращаемого значения, добавив двоеточие и тип после последнего параметра.</span><span class="sxs-lookup"><span data-stu-id="f1abc-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="f1abc-126">Полные аннотации типа для `function1`, в качестве типов параметров которых есть целые числа, будут выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f1abc-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="f1abc-127">Если нет явных параметров типа, для определения типов параметров функций используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="f1abc-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="f1abc-128">Это может включать автоматическое обобщение типа параметра как универсального.</span><span class="sxs-lookup"><span data-stu-id="f1abc-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="f1abc-129">Дополнительные сведения см. в разделе [Автоматическое обобщение](../generics/automatic-generalization.md) и [Вывод типов](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f1abc-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="f1abc-130">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="f1abc-130">let Bindings in Classes</span></span>

<span data-ttu-id="f1abc-131">`let` Привязка может присутствовать в типе класса, но не в типе структуры или записи.</span><span class="sxs-lookup"><span data-stu-id="f1abc-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="f1abc-132">Чтобы использовать привязку let в типе класса, класс должен иметь первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="f1abc-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="f1abc-133">Параметры конструктора должны находиться после имени типа в определении класса.</span><span class="sxs-lookup"><span data-stu-id="f1abc-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="f1abc-134">Привязка в типе класса определяет закрытые поля и члены для этого типа класса, а вместе с `do` привязками в типе формирует код для первичного конструктора для типа. `let`</span><span class="sxs-lookup"><span data-stu-id="f1abc-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="f1abc-135">В следующих примерах кода показан класс `MyClass` с закрытыми `field1` полями `field2`и.</span><span class="sxs-lookup"><span data-stu-id="f1abc-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="f1abc-136">Области `field1` и`field2` ограничены типом, в котором они объявляются.</span><span class="sxs-lookup"><span data-stu-id="f1abc-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="f1abc-137">Дополнительные сведения см. [ `let` в разделе привязки в классах](../members/let-bindings-in-classes.md) и [классах](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="f1abc-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="f1abc-138">Параметры типа в привязках let</span><span class="sxs-lookup"><span data-stu-id="f1abc-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="f1abc-139">`let` Привязка на уровне модуля, в типе или в вычислительном выражении может иметь явные параметры типа.</span><span class="sxs-lookup"><span data-stu-id="f1abc-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="f1abc-140">Привязка let в выражении, например в определении функции, не может иметь параметры типа.</span><span class="sxs-lookup"><span data-stu-id="f1abc-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="f1abc-141">Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="f1abc-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="f1abc-142">Атрибуты в привязках let</span><span class="sxs-lookup"><span data-stu-id="f1abc-142">Attributes on let Bindings</span></span>

<span data-ttu-id="f1abc-143">Атрибуты могут применяться к привязкам верхнего уровня `let` в модуле, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f1abc-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="f1abc-144">Область и доступность привязок let</span><span class="sxs-lookup"><span data-stu-id="f1abc-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="f1abc-145">Область сущности, объявленной с привязкой let, ограничена частью содержащей его области (например, функции, модуля, файла или класса) после отображения привязки.</span><span class="sxs-lookup"><span data-stu-id="f1abc-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="f1abc-146">Таким образом, можно сказать, что привязка let вводит имя в область.</span><span class="sxs-lookup"><span data-stu-id="f1abc-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="f1abc-147">В модуле значение, привязанное к let, может быть доступно клиентам модуля, если модуль доступен, так как привязки let в модуле компилируются в открытые функции модуля.</span><span class="sxs-lookup"><span data-stu-id="f1abc-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="f1abc-148">В отличие от этого, привязки let в классе являются частными для класса.</span><span class="sxs-lookup"><span data-stu-id="f1abc-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="f1abc-149">Обычно функции в модулях должны уточняться именем модуля при использовании клиентского кода.</span><span class="sxs-lookup"><span data-stu-id="f1abc-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="f1abc-150">Например, если модуль `Module1` содержит функцию `function1`, пользователи будут `Module1.function1` ссылаться на функцию.</span><span class="sxs-lookup"><span data-stu-id="f1abc-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="f1abc-151">Пользователи модуля могут использовать объявление импорта, чтобы сделать функции в этом модуле доступными для использования без уточнения по имени модуля.</span><span class="sxs-lookup"><span data-stu-id="f1abc-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="f1abc-152">В этом примере пользователи модуля могут открыть модуль с помощью открытого `Module1` объявления импорта, а затем напрямую обратиться к `function1` нему.</span><span class="sxs-lookup"><span data-stu-id="f1abc-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="f1abc-153">Некоторые модули имеют атрибут [рекуирекуалифиедакцесс](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), что означает, что предоставляемые им функции должны уточняться именем модуля.</span><span class="sxs-lookup"><span data-stu-id="f1abc-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="f1abc-154">Например, у модуля F# List есть этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="f1abc-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="f1abc-155">Дополнительные сведения о модулях и контроле доступа см. в разделе [модули](../modules.md) и [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="f1abc-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1abc-156">См. также</span><span class="sxs-lookup"><span data-stu-id="f1abc-156">See also</span></span>

- [<span data-ttu-id="f1abc-157">Функции</span><span class="sxs-lookup"><span data-stu-id="f1abc-157">Functions</span></span>](index.md)
- [<span data-ttu-id="f1abc-158">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="f1abc-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
