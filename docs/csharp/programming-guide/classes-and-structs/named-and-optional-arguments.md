---
title: Руководство по программированию на C#. Именованные и необязательные аргументы
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: df590cf9d18b6de81caccfb77e544451da9ee0df
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244912"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="3cd10-102">Именованные и необязательные аргументы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3cd10-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] <span data-ttu-id="3cd10-103">вводит именованные и необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="3cd10-103">introduces named and optional arguments.</span></span> <span data-ttu-id="3cd10-104">*Именованные аргументы* позволяют указать аргумент для определенного параметра, связав этот аргумент с именем параметра, а не с его позицией в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="3cd10-105">*Необязательные аргументы* позволяют опускать аргументы для некоторых параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="3cd10-106">Оба варианта можно использовать с методами, индексаторами, конструкторами и делегатами.</span><span class="sxs-lookup"><span data-stu-id="3cd10-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="3cd10-107">При использовании именованных и необязательных аргументов аргументы оцениваются в том порядке, в котором они отображаются в списке аргументов, а не в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="3cd10-108">При совместном использовании именованные и необязательные параметры позволяют задавать аргументы только для некоторых параметров из списка необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="3cd10-109">Эта возможность значительно упрощает вызов интерфейсов COM, таких как API автоматизации Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="3cd10-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="3cd10-110">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="3cd10-110">Named Arguments</span></span>  
 <span data-ttu-id="3cd10-111">Именованные аргументы освобождают разработчика от необходимости запоминать или уточнять порядок параметров в списках параметров вызванных методов.</span><span class="sxs-lookup"><span data-stu-id="3cd10-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="3cd10-112">Параметр для каждого аргумента можно указать, используя имя параметра.</span><span class="sxs-lookup"><span data-stu-id="3cd10-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="3cd10-113">Например, функция, которая выводит сведения о заказе (например, имя продавца, номер заказа и наименование товара), может вызываться как обычно, путем передачи аргументов по позиции в порядке, определяемом функцией.</span><span class="sxs-lookup"><span data-stu-id="3cd10-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="3cd10-114">Если вы не помните порядок параметров, но знаете их имена, можете передать аргументы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="3cd10-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="3cd10-115">Именованные аргументы также делают код более удобным для чтения, поскольку указывают, чему соответствует каждый аргумент.</span><span class="sxs-lookup"><span data-stu-id="3cd10-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="3cd10-116">В приведенном ниже примере метода `sellerName` не может быть равен NULL или пробелу.</span><span class="sxs-lookup"><span data-stu-id="3cd10-116">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="3cd10-117">Так как и `sellerName`, и `productName` являются строковыми типами, вместо передачи аргументов по позиции имеет смысл использовать именованные аргументы, чтобы устранить данную неоднозначность и сделать код более удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="3cd10-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="3cd10-118">Именованные аргументы при использовании с позиционными аргументами допустимы при условии, что</span><span class="sxs-lookup"><span data-stu-id="3cd10-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="3cd10-119">за ними не следуют позиционные аргументы, либо,</span><span class="sxs-lookup"><span data-stu-id="3cd10-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="3cd10-120">_начиная с C# 7.2_, они используются в правильной позиции.</span><span class="sxs-lookup"><span data-stu-id="3cd10-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="3cd10-121">В примере ниже параметр `orderNum` находится в правильной позиции, но не имеет явно заданного имени.</span><span class="sxs-lookup"><span data-stu-id="3cd10-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="3cd10-122">Однако внеочередные именованные аргументы недопустимы, если за ними следуют позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="3cd10-122">However, out-of-order named arguments are invalid if they're followed by positional arguments.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="3cd10-123">Пример</span><span class="sxs-lookup"><span data-stu-id="3cd10-123">Example</span></span>  
 <span data-ttu-id="3cd10-124">Приведенный ниже код реализует как примеры из этого раздела, так и некоторые дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="3cd10-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="3cd10-125">Необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="3cd10-125">Optional Arguments</span></span>  
 <span data-ttu-id="3cd10-126">Определение метода, конструктора, индексатора или делегата может указывать, являются его параметры обязательными или нет.</span><span class="sxs-lookup"><span data-stu-id="3cd10-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="3cd10-127">Любой вызов должен содержать аргументы для всех обязательных параметров; аргументы для необязательных параметров можно опустить.</span><span class="sxs-lookup"><span data-stu-id="3cd10-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="3cd10-128">Определение каждого необязательного параметра содержит его значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cd10-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="3cd10-129">Если аргумент для параметра не передается, используется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cd10-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="3cd10-130">Значением по умолчанию должен быть один из следующих типов выражений:</span><span class="sxs-lookup"><span data-stu-id="3cd10-130">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="3cd10-131">константное выражение;</span><span class="sxs-lookup"><span data-stu-id="3cd10-131">a constant expression;</span></span>  
  
-   <span data-ttu-id="3cd10-132">выражение в форме `new ValType()`, где `ValType` — это тип значения, например, [enum](../../../csharp/language-reference/keywords/enum.md) или [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span><span class="sxs-lookup"><span data-stu-id="3cd10-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="3cd10-133">выражение в форме [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), где `ValType` — это тип значения.</span><span class="sxs-lookup"><span data-stu-id="3cd10-133">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="3cd10-134">Необязательные параметры определяются в конце списка параметров после всех обязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="3cd10-135">Если вызывающий объект предоставляет аргумент для любого из последующих необязательных параметров, он должен содержать аргументы для всех предыдущих необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="3cd10-136">Пробелы, разделенные запятыми, в списке аргументов не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3cd10-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="3cd10-137">Например, в следующем коде метод экземпляра `ExampleMethod` определяется одним обязательным и двумя необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="3cd10-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 <span data-ttu-id="3cd10-138">Следующий вызов `ExampleMethod` вызывает ошибку компилятора, поскольку аргумент предоставляется для третьего параметра, но не для второго.</span><span class="sxs-lookup"><span data-stu-id="3cd10-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="3cd10-139">Если вы знаете имя третьего параметра, можете использовать для выполнения задачи именованный аргумент.</span><span class="sxs-lookup"><span data-stu-id="3cd10-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="3cd10-140">В IntelliSense необязательные параметры заключаются в квадратные скобки, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="3cd10-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="3cd10-141">![Быстрая справка IntelliSense для метода ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="3cd10-141">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="3cd10-142">Необязательные параметры в ExampleMethod</span><span class="sxs-lookup"><span data-stu-id="3cd10-142">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cd10-143">Необязательные параметры также можно объявлять с помощью класса .NET <xref:System.Runtime.InteropServices.OptionalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3cd10-143">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="3cd10-144">Для параметров `OptionalAttribute` значение по умолчанию не требуется.</span><span class="sxs-lookup"><span data-stu-id="3cd10-144">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd10-145">Пример</span><span class="sxs-lookup"><span data-stu-id="3cd10-145">Example</span></span>  
 <span data-ttu-id="3cd10-146">В следующем примере конструктор `ExampleClass` имеет один параметр, который является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3cd10-146">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="3cd10-147">У метода экземпляра `ExampleMethod` есть один обязательный параметр, `required`, и два необязательных параметра, `optionalstr` и `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="3cd10-147">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="3cd10-148">Код в `Main` демонстрирует различные способы, которые можно использовать для вызова конструктора и метода.</span><span class="sxs-lookup"><span data-stu-id="3cd10-148">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="3cd10-149">Интерфейсы COM</span><span class="sxs-lookup"><span data-stu-id="3cd10-149">COM Interfaces</span></span>  
 <span data-ttu-id="3cd10-150">Именованные и необязательные аргументы, а также поддержка динамических объектов и другие усовершенствования значительно улучшают взаимодействие с API COM, такими как API автоматизации Office.</span><span class="sxs-lookup"><span data-stu-id="3cd10-150">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="3cd10-151">Например, метод <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A>в интерфейсе Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> имеет семь параметров и все они необязательные.</span><span class="sxs-lookup"><span data-stu-id="3cd10-151">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="3cd10-152">Эти параметры показаны на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="3cd10-152">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="3cd10-153">![Быстрая справка IntelliSense для метода AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="3cd10-153">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="3cd10-154">Параметры метода AutoFormat</span><span class="sxs-lookup"><span data-stu-id="3cd10-154">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="3cd10-155">В C# 3.0 и более ранних версиях аргумент необходимо указывать для каждого параметра, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3cd10-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 <span data-ttu-id="3cd10-156">При этом вызов `AutoFormat` можно значительно упростить, используя именованные и необязательные аргументы, представленные в C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="3cd10-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="3cd10-157">Именованные и необязательные аргументы позволяют опускать аргументы для необязательных параметров, если значение параметра по умолчанию менять не нужно.</span><span class="sxs-lookup"><span data-stu-id="3cd10-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="3cd10-158">В следующем вызове значение задается только для одного из семи параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 <span data-ttu-id="3cd10-159">Дополнительные сведения и примеры см. в статьях [Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) и [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="3cd10-159">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="3cd10-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="3cd10-160">Overload Resolution</span></span>  
 <span data-ttu-id="3cd10-161">Использование именованных и необязательных аргументов влияет на разрешение перегрузки описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="3cd10-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="3cd10-162">Метод, индексатор или конструктор является кандидатом на выполнение, если каждый из его параметров необязателен либо по имени или позиции соответствует одному и тому же аргументу в операторе вызова, и этот аргумент можно преобразовать в тип параметра.</span><span class="sxs-lookup"><span data-stu-id="3cd10-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="3cd10-163">Если найдено более одного кандидата, правила разрешения перегрузки для предпочтительных преобразований применяются к аргументам, указанным явно.</span><span class="sxs-lookup"><span data-stu-id="3cd10-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="3cd10-164">Опущенные аргументы для необязательных параметров игнорируются.</span><span class="sxs-lookup"><span data-stu-id="3cd10-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="3cd10-165">Если два кандидата определяются как равно подходящие, предпочтение отдается кандидату без необязательных параметров, аргументы которых в вызове были опущены.</span><span class="sxs-lookup"><span data-stu-id="3cd10-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="3cd10-166">Это — последовательность определения приоритетов в разрешении перегрузки для кандидатов с меньшим числом параметров.</span><span class="sxs-lookup"><span data-stu-id="3cd10-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3cd10-167">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3cd10-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cd10-168">См. также</span><span class="sxs-lookup"><span data-stu-id="3cd10-168">See Also</span></span>

- [<span data-ttu-id="3cd10-169">Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office</span><span class="sxs-lookup"><span data-stu-id="3cd10-169">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
- [<span data-ttu-id="3cd10-170">Использование типа dynamic</span><span class="sxs-lookup"><span data-stu-id="3cd10-170">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [<span data-ttu-id="3cd10-171">Использование конструкторов</span><span class="sxs-lookup"><span data-stu-id="3cd10-171">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
- [<span data-ttu-id="3cd10-172">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="3cd10-172">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)
