---
title: Привязки let
description: Сведения об использовании F# «let» привязка, которая связывает идентификатор со значением или функцией.
ms.date: 05/16/2016
ms.openlocfilehash: ac33ee761cd4881f3d82d6680a07f62a1d7e77e5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641897"
---
# <a name="let-bindings"></a><span data-ttu-id="7e2e7-103">Привязки let</span><span class="sxs-lookup"><span data-stu-id="7e2e7-103">let Bindings</span></span>

<span data-ttu-id="7e2e7-104">Объект *привязки* связывает идентификатор со значением или функцией.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="7e2e7-105">Использовании `let` ключевое слово для привязки имени значением или функцией.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e2e7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e2e7-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="7e2e7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e2e7-107">Remarks</span></span>

<span data-ttu-id="7e2e7-108">`let` В привязке выражений для определения значений или значений функции для одного или нескольких имен используется ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="7e2e7-109">Самая простая форма `let` выражение связывает имя с простым значением, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="7e2e7-110">Если разделить выражение из идентификатора с помощью строки, вы должны отступить в каждой строке выражения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="7e2e7-111">Вместо простого имени можно указать шаблон, который содержит имена, например, кортеж, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="7e2e7-112">*Телом выражения* является выражением, в котором используются имена.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="7e2e7-113">Выражение тела находится на отдельной строке, строке вверх с отступом первого символа в `let` ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="7e2e7-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="7e2e7-114">Объект `let` привязки может отображаться на уровне модуля, в определении типа класса или в локальных областях, например в определении функции.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="7e2e7-115">Объект `let` привязки на верхнем уровне в модуле или в типе класса выражении тела не требуется, но на других уровнях областей телом выражения является обязательным.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="7e2e7-116">Привязанные имена можно использовать после точки определения, но не на любом этапе до `let` появится привязки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="7e2e7-117">Привязки функций</span><span class="sxs-lookup"><span data-stu-id="7e2e7-117">Function Bindings</span></span>

<span data-ttu-id="7e2e7-118">Привязки функций соответствовать правилам для привязки значений, за исключением того, что функция привязки включают в себя имя функции и параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="7e2e7-119">Как правило используются следующие параметры. шаблоны, такие как шаблон кортежа</span><span class="sxs-lookup"><span data-stu-id="7e2e7-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="7e2e7-120">Объект `let` выражение привязки имеет значение последнего выражения.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="7e2e7-121">Таким образом, в следующем примере кода значение `result` вычисляется на основе `100 * function3 (1, 2)`, результатом которого является `300`.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="7e2e7-122">См. дополнительные сведения о [функциях](index.md).</span><span class="sxs-lookup"><span data-stu-id="7e2e7-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="7e2e7-123">Аннотации типов</span><span class="sxs-lookup"><span data-stu-id="7e2e7-123">Type Annotations</span></span>

<span data-ttu-id="7e2e7-124">Можно указать типы для параметров, включая двоеточие (:), за которым следует имя типа, заключенного в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="7e2e7-125">Можно также указать тип возвращаемого значения, добавив двоеточие и тип после последнего параметра.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="7e2e7-126">Полные аннотации типа для `function1`, с целыми числами, как типы параметра, будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="7e2e7-127">При отсутствии параметров явный тип, определение типа используется для определения типов параметров функций.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="7e2e7-128">Они могут включать Автоматическое обобщение типа параметра быть универсальными.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="7e2e7-129">Дополнительные сведения см. в разделе [Автоматическое обобщение](../generics/automatic-generalization.md) и [вывод типа](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="7e2e7-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="7e2e7-130">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="7e2e7-130">let Bindings in Classes</span></span>

<span data-ttu-id="7e2e7-131">Объект `let` привязки может находиться в типе класса, но не в структуре или тип записи.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="7e2e7-132">Чтобы использовать привязку let в тип класса, этот класс должен иметь первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="7e2e7-133">Параметры конструктора должны находиться после имени типа в определении класса.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="7e2e7-134">Объект `let` привязки в типе класса определяет закрытые поля и члены для этого типа класса и вместе с `do` привязок в типе, формирует код первичного конструктора для типа.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="7e2e7-135">В следующем примере кода показан класс `MyClass` с закрытыми полями `field1` и `field2`.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="7e2e7-136">Области `field1` и `field2` ограничены в тип, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="7e2e7-137">Дополнительные сведения см. в разделе [ `let` привязок в классах](../members/let-bindings-in-classes.md) и [классы](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="7e2e7-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="7e2e7-138">Параметры типа в привязки let</span><span class="sxs-lookup"><span data-stu-id="7e2e7-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="7e2e7-139">Объект `let` привязки на уровне модуля, в типе или в вычислительном выражении может иметь явные параметры типов.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="7e2e7-140">Привязка let в выражения, такие как в определении функции не может иметь параметры типа.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="7e2e7-141">Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="7e2e7-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="7e2e7-142">Атрибуты привязки let</span><span class="sxs-lookup"><span data-stu-id="7e2e7-142">Attributes on let Bindings</span></span>

<span data-ttu-id="7e2e7-143">Атрибуты могут применяться к верхнего уровня `let` привязок в модуле, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="7e2e7-144">Область и специальные возможности привязки Let</span><span class="sxs-lookup"><span data-stu-id="7e2e7-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="7e2e7-145">Область сущности, объявленной с помощью привязки let ограничено к той части, содержащего область (например, функции, модуля, файла или класса), после появления привязки.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="7e2e7-146">Таким образом можно сказать, что привязка let вводит имя в область действия.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="7e2e7-147">В модуле привязки let значением или функцией доступен клиентам модуля до тех пор, пока модуль доступен, так как привязки let в модуле компилируются в открытых функций модуля.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="7e2e7-148">Напротив привязки let в классе являются частными к классу.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="7e2e7-149">Как правило функции в модулях должны уточняться именем модуля, при использовании в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="7e2e7-150">Например, если модуль `Module1` имеет функцию `function1`, пользователи будут указывать `Module1.function1` для ссылки на функцию.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="7e2e7-151">Пользователи модуля, могут использовать объявление импорта, чтобы сделать доступными для использования функции в этом модуле без имен имя модуля.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="7e2e7-152">В примере упомянутых пользователям этого модуля в этом случае можно открыть модуль с помощью функции открытия объявление импорта `Module1` и затем ссылаться на `function1` напрямую.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="7e2e7-153">Некоторые модули имеют атрибут [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), что означает, что функции, которые они предоставляют должны быть дополнены именем модуля.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="7e2e7-154">Например F# модуля "список" с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="7e2e7-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="7e2e7-155">Дополнительные сведения о модулях и управление доступом, см. в разделе [модули](../modules.md) и [контроля доступа](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="7e2e7-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e2e7-156">См. также</span><span class="sxs-lookup"><span data-stu-id="7e2e7-156">See also</span></span>

- [<span data-ttu-id="7e2e7-157">Функции</span><span class="sxs-lookup"><span data-stu-id="7e2e7-157">Functions</span></span>](index.md)
- [<span data-ttu-id="7e2e7-158">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="7e2e7-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
