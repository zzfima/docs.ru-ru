---
title: Привязки let (F#)
description: 'Сведения об использовании F #, «let» привязка, которая связывает идентификатор со значением или функцией.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 2abc4e05f9f2977501f01f745062e2e7cd611f68
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="let-bindings"></a><span data-ttu-id="823a3-103">Привязки let</span><span class="sxs-lookup"><span data-stu-id="823a3-103">let Bindings</span></span>

<span data-ttu-id="823a3-104">Объект *привязки* связывает идентификатор со значением или функцией.</span><span class="sxs-lookup"><span data-stu-id="823a3-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="823a3-105">Вы используете `let` ключевое слово для привязки имени к значению или функции.</span><span class="sxs-lookup"><span data-stu-id="823a3-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="823a3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="823a3-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="823a3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="823a3-107">Remarks</span></span>

<span data-ttu-id="823a3-108">`let` В привязке выражений для определения значений или функциональных значений одного или нескольких имен используется ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="823a3-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="823a3-109">Самая простая форма `let` выражение привязывает имя к простому значению, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="823a3-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="823a3-110">Если разделить выражение идентификатор с помощью строки, необходимо отступ каждой строки выражения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="823a3-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="823a3-111">Вместо простого имени можно указать шаблон, который содержит имена, например, кортеж, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="823a3-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="823a3-112">*Выражение тела* — выражение, в котором используются имена.</span><span class="sxs-lookup"><span data-stu-id="823a3-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="823a3-113">Выражение тела находится на отдельной строке строку вверх с отступом первого символа в `let` ключевое слово:</span><span class="sxs-lookup"><span data-stu-id="823a3-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="823a3-114">Объект `let` привязки могут отображаться на уровне модуля, в определении типа класса или в локальных областях, например в определении функции.</span><span class="sxs-lookup"><span data-stu-id="823a3-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="823a3-115">Объект `let` привязки на верхнем уровне в модуле или в типе класса выражении тела не требуется, но на других уровнях областей выражение тела не требуется.</span><span class="sxs-lookup"><span data-stu-id="823a3-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="823a3-116">Привязанные имена можно использовать после точки определения, но не в любой момент перед `let` появится привязки, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="823a3-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a><span data-ttu-id="823a3-117">Функции привязок</span><span class="sxs-lookup"><span data-stu-id="823a3-117">Function Bindings</span></span>

<span data-ttu-id="823a3-118">Привязка функции соответствовать правилам для привязки значений, за исключением того, что функция привязки включают в себя имя функции и параметры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="823a3-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="823a3-119">Как правило используются следующие параметры шаблонов, таких как шаблон кортежа.</span><span class="sxs-lookup"><span data-stu-id="823a3-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="823a3-120">Объект `let` выражение привязки имеет значение последнего выражения.</span><span class="sxs-lookup"><span data-stu-id="823a3-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="823a3-121">Таким образом, в следующем примере кода значение `result` вычисляется на основе `100 * function3 (1, 2)`, результатом которого является `300`.</span><span class="sxs-lookup"><span data-stu-id="823a3-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="823a3-122">См. дополнительные сведения о [функциях](index.md).</span><span class="sxs-lookup"><span data-stu-id="823a3-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="823a3-123">Аннотации типов</span><span class="sxs-lookup"><span data-stu-id="823a3-123">Type Annotations</span></span>

<span data-ttu-id="823a3-124">Можно указать типы для параметров, включая двоеточие (:), за которым следует имя типа, заключенного в скобки.</span><span class="sxs-lookup"><span data-stu-id="823a3-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="823a3-125">Также можно указать тип возвращаемого значения, добавив двоеточие и тип после последнего параметра.</span><span class="sxs-lookup"><span data-stu-id="823a3-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="823a3-126">Полные аннотации типа для `function1`, с целочисленными значениями как типы параметра будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="823a3-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="823a3-127">Если нет явных параметров типа, определение типа используется для определения типов параметров функций.</span><span class="sxs-lookup"><span data-stu-id="823a3-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="823a3-128">Это может включать Автоматическое обобщение типа параметра, как универсальные.</span><span class="sxs-lookup"><span data-stu-id="823a3-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="823a3-129">Дополнительные сведения см. в разделе [Автоматическое обобщение](../generics/automatic-generalization.md) и [вывод типа](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="823a3-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="823a3-130">Привязки let в классах</span><span class="sxs-lookup"><span data-stu-id="823a3-130">let Bindings in Classes</span></span>

<span data-ttu-id="823a3-131">Объект `let` привязки может находиться в типе класса, но не в структуре или тип записи.</span><span class="sxs-lookup"><span data-stu-id="823a3-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="823a3-132">Чтобы использовать привязку let в типе класса, класс должен иметь первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="823a3-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="823a3-133">Параметры конструктора должен находиться после имени типа в определении класса.</span><span class="sxs-lookup"><span data-stu-id="823a3-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="823a3-134">Объект `let` привязки в типе класса определяет закрытые поля и члены для этого типа класса и вместе с `do` привязок в типе, формирует код первичного конструктора для типа.</span><span class="sxs-lookup"><span data-stu-id="823a3-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="823a3-135">В следующем примере кода показан класс `MyClass` с закрытыми полями `field1` и `field2`.</span><span class="sxs-lookup"><span data-stu-id="823a3-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="823a3-136">Области `field1` и `field2` ограничены тип, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="823a3-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="823a3-137">Дополнительные сведения см. в разделе [ `let` привязок в классах](../members/let-bindings-in-classes.md) и [классы](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="823a3-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="823a3-138">Привязки let параметров типа в</span><span class="sxs-lookup"><span data-stu-id="823a3-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="823a3-139">Объект `let` привязки на уровне модуля в типе или в вычислительном выражении может иметь явные параметры типов.</span><span class="sxs-lookup"><span data-stu-id="823a3-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="823a3-140">Привязку let в выражении, например в определении функции не может иметь параметров типа.</span><span class="sxs-lookup"><span data-stu-id="823a3-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="823a3-141">Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="823a3-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="823a3-142">Атрибуты привязок let</span><span class="sxs-lookup"><span data-stu-id="823a3-142">Attributes on let Bindings</span></span>

<span data-ttu-id="823a3-143">Атрибуты могут применяться к верхнего уровня `let` привязки в модуле, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="823a3-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="823a3-144">Область действия и доступность привязки Let</span><span class="sxs-lookup"><span data-stu-id="823a3-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="823a3-145">Сущности, объявленной с помощью привязки let относится только часть, содержащая область (например, функции, модуля, файла или класса), после появления привязки.</span><span class="sxs-lookup"><span data-stu-id="823a3-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="823a3-146">Таким образом можно назвать, что привязки let вводит имя в области.</span><span class="sxs-lookup"><span data-stu-id="823a3-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="823a3-147">В модуле значение привязки let или функция доступен клиентам модуля при условии, что модуль недоступна, так как привязки let в модуле компилируются в открытых функций модуля.</span><span class="sxs-lookup"><span data-stu-id="823a3-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="823a3-148">В отличие от этого привязки let в классе являются закрытыми для класса.</span><span class="sxs-lookup"><span data-stu-id="823a3-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="823a3-149">Как правило функции в модулях должно быть дополнено именем модуля, при использовании в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="823a3-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="823a3-150">Например, если модуль `Module1` имеет функцию `function1`, пользователи будут указывать `Module1.function1` для ссылки на функцию.</span><span class="sxs-lookup"><span data-stu-id="823a3-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="823a3-151">Пользователи модуля могут использовать объявление импорта, чтобы сделать доступными для использования функций в этом модуле без имен имя модуля.</span><span class="sxs-lookup"><span data-stu-id="823a3-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="823a3-152">В упомянутой выше примере пользователям этого модуля в этом случае можно открыть модуль с помощью open объявление импорта `Module1` и затем ссылаться на `function1` напрямую.</span><span class="sxs-lookup"><span data-stu-id="823a3-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="823a3-153">Некоторые модули имеют атрибут [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), что означает, что функции, которые они предоставляют должны быть дополнены именем модуля.</span><span class="sxs-lookup"><span data-stu-id="823a3-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="823a3-154">Например модуль F # список имеет этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="823a3-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="823a3-155">Дополнительные сведения о модулях и управления доступом см. в разделе [модули](../modules.md) и [управления доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="823a3-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="823a3-156">См. также</span><span class="sxs-lookup"><span data-stu-id="823a3-156">See Also</span></span>

[<span data-ttu-id="823a3-157">Функции</span><span class="sxs-lookup"><span data-stu-id="823a3-157">Functions</span></span>](index.md)

[<span data-ttu-id="823a3-158">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="823a3-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
