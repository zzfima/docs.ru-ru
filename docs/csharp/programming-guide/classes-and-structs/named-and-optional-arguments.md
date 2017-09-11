---
title: "Именованные и необязательные аргументы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: a7f05e3e0b19bf6457989f8db2b46741cf6b28c1
ms.contentlocale: ru-ru
ms.lasthandoff: 08/29/2017

---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="78a89-102">Именованные и необязательные аргументы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="78a89-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="78a89-103"> вводит именованные и необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="78a89-103"> introduces named and optional arguments.</span></span> <span data-ttu-id="78a89-104">*Именованные аргументы* позволяют указать аргумент для определенного параметра, связав этот аргумент с именем параметра, а не с его позицией в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="78a89-105">*Необязательные аргументы* позволяют опускать аргументы для некоторых параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="78a89-106">Оба варианта можно использовать с методами, индексаторами, конструкторами и делегатами.</span><span class="sxs-lookup"><span data-stu-id="78a89-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="78a89-107">При использовании именованных и необязательных аргументов аргументы оцениваются в том порядке, в котором они отображаются в списке аргументов, а не в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="78a89-108">При совместном использовании именованные и необязательные параметры позволяют задавать аргументы только для некоторых параметров из списка необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="78a89-109">Эта возможность значительно упрощает вызов интерфейсов COM, таких как API автоматизации Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="78a89-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="78a89-110">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="78a89-110">Named Arguments</span></span>  
 <span data-ttu-id="78a89-111">Именованные аргументы освобождают разработчика от необходимости запоминать или уточнять порядок параметров в списках параметров вызванных методов.</span><span class="sxs-lookup"><span data-stu-id="78a89-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="78a89-112">Параметр для каждого аргумента можно указать, используя имя параметра.</span><span class="sxs-lookup"><span data-stu-id="78a89-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="78a89-113">Например, функция, которая вычисляет индекс массы тела (BMI), может вызываться как обычно, путем передачи аргументов для веса и роста по позиции в порядке, определяемом функцией.</span><span class="sxs-lookup"><span data-stu-id="78a89-113">For example, a function that calculates body mass index (BMI) can be called in the standard way by sending arguments for weight and height by position, in the order defined by the function.</span></span>  
  
 `CalculateBMI(123, 64);`  
  
 <span data-ttu-id="78a89-114">Если вы не помните порядок параметров, но знаете их имена, можете передать аргументы в любом порядке, начиная либо с веса, либо с роста.</span><span class="sxs-lookup"><span data-stu-id="78a89-114">If you do not remember the order of the parameters but you do know their names, you can send the arguments in either order, weight first or height first.</span></span>  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 <span data-ttu-id="78a89-115">Именованные аргументы также делают код более удобным для чтения, поскольку указывают, чему соответствует каждый аргумент.</span><span class="sxs-lookup"><span data-stu-id="78a89-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span>  
  
 <span data-ttu-id="78a89-116">Именованный аргумент может следовать за позиционными аргументами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="78a89-116">A named argument can follow positional arguments, as shown here.</span></span>  
  
 `CalculateBMI(123, height: 64);`  
  
 <span data-ttu-id="78a89-117">При этом за именованным аргументом позиционный аргумент идти не может.</span><span class="sxs-lookup"><span data-stu-id="78a89-117">However, a positional argument cannot follow a named argument.</span></span> <span data-ttu-id="78a89-118">Следующий код вызывает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="78a89-118">The following statement causes a compiler error.</span></span>  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## <a name="example"></a><span data-ttu-id="78a89-119">Пример</span><span class="sxs-lookup"><span data-stu-id="78a89-119">Example</span></span>  
 <span data-ttu-id="78a89-120">Следующий код реализует примеры из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="78a89-120">The following code implements the examples from this section.</span></span>  
  
 <span data-ttu-id="78a89-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="78a89-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span></span>  
  
## <a name="optional-arguments"></a><span data-ttu-id="78a89-122">Необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="78a89-122">Optional Arguments</span></span>  
 <span data-ttu-id="78a89-123">Определение метода, конструктора, индексатора или делегата может указывать, являются его параметры обязательными или нет.</span><span class="sxs-lookup"><span data-stu-id="78a89-123">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="78a89-124">Любой вызов должен содержать аргументы для всех обязательных параметров; аргументы для необязательных параметров можно опустить.</span><span class="sxs-lookup"><span data-stu-id="78a89-124">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="78a89-125">Определение каждого необязательного параметра содержит его значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="78a89-125">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="78a89-126">Если аргумент для параметра не передается, используется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="78a89-126">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="78a89-127">Значением по умолчанию должен быть один из следующих типов выражений:</span><span class="sxs-lookup"><span data-stu-id="78a89-127">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="78a89-128">константное выражение;</span><span class="sxs-lookup"><span data-stu-id="78a89-128">a constant expression;</span></span>  
  
-   <span data-ttu-id="78a89-129">выражение в форме `new ValType()`, где `ValType` — это тип значения, например, [enum](../../../csharp/language-reference/keywords/enum.md) или [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span><span class="sxs-lookup"><span data-stu-id="78a89-129">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="78a89-130">выражение в форме [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), где `ValType` — это тип значения.</span><span class="sxs-lookup"><span data-stu-id="78a89-130">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="78a89-131">Необязательные параметры определяются в конце списка параметров после всех обязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-131">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="78a89-132">Если вызывающий объект предоставляет аргумент для любого из последующих необязательных параметров, он должен содержать аргументы для всех предыдущих необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-132">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="78a89-133">Пробелы, разделенные запятыми, в списке аргументов не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="78a89-133">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="78a89-134">Например, в следующем коде метод экземпляра `ExampleMethod` определяется одним обязательным и двумя необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="78a89-134">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 <span data-ttu-id="78a89-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="78a89-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="78a89-136">Следующий вызов `ExampleMethod` вызывает ошибку компилятора, поскольку аргумент предоставляется для третьего параметра, но не для второго.</span><span class="sxs-lookup"><span data-stu-id="78a89-136">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="78a89-137">Если вы знаете имя третьего параметра, можете использовать для выполнения задачи именованный аргумент.</span><span class="sxs-lookup"><span data-stu-id="78a89-137">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="78a89-138">В IntelliSense необязательные параметры заключаются в квадратные скобки, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="78a89-138">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="78a89-139">![Быстрая справка IntelliSense для метода ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="78a89-139">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="78a89-140">Необязательные параметры в ExampleMethod</span><span class="sxs-lookup"><span data-stu-id="78a89-140">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78a89-141">Необязательные параметры также можно объявлять с помощью класса .NET <xref:System.Runtime.InteropServices.OptionalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="78a89-141">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="78a89-142">Для параметров `OptionalAttribute` значение по умолчанию не требуется.</span><span class="sxs-lookup"><span data-stu-id="78a89-142">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78a89-143">Пример</span><span class="sxs-lookup"><span data-stu-id="78a89-143">Example</span></span>  
 <span data-ttu-id="78a89-144">В следующем примере конструктор `ExampleClass` имеет один параметр, который является необязательным.</span><span class="sxs-lookup"><span data-stu-id="78a89-144">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="78a89-145">У метода экземпляра `ExampleMethod` есть один обязательный параметр, `required`, и два необязательных параметра, `optionalstr` и `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="78a89-145">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="78a89-146">Код в `Main` демонстрирует различные способы, которые можно использовать для вызова конструктора и метода.</span><span class="sxs-lookup"><span data-stu-id="78a89-146">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 <span data-ttu-id="78a89-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="78a89-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span></span>  
  
## <a name="com-interfaces"></a><span data-ttu-id="78a89-148">Интерфейсы COM</span><span class="sxs-lookup"><span data-stu-id="78a89-148">COM Interfaces</span></span>  
 <span data-ttu-id="78a89-149">Именованные и необязательные аргументы, а также поддержка динамических объектов и другие усовершенствования значительно улучшают взаимодействие с API COM, такими как API автоматизации Office.</span><span class="sxs-lookup"><span data-stu-id="78a89-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="78a89-150">Например, метод [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) в интерфейсе [диапазона](http://go.microsoft.com/fwlink/?LinkId=148196) Microsoft Office Excel имеет семь параметров и все они необязательные.</span><span class="sxs-lookup"><span data-stu-id="78a89-150">For example, the [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) method in the Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="78a89-151">Эти параметры показаны на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="78a89-151">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="78a89-152">![Быстрая справка IntelliSense для метода AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="78a89-152">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="78a89-153">Параметры метода AutoFormat</span><span class="sxs-lookup"><span data-stu-id="78a89-153">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="78a89-154">В C# 3.0 и более ранних версиях аргумент необходимо указывать для каждого параметра, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="78a89-154">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 <span data-ttu-id="78a89-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="78a89-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span></span>  
  
 <span data-ttu-id="78a89-156">При этом вызов `AutoFormat` можно значительно упростить, используя именованные и необязательные аргументы, представленные в C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="78a89-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="78a89-157">Именованные и необязательные аргументы позволяют опускать аргументы для необязательных параметров, если значение параметра по умолчанию менять не нужно.</span><span class="sxs-lookup"><span data-stu-id="78a89-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="78a89-158">В следующем вызове значение задается только для одного из семи параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 <span data-ttu-id="78a89-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="78a89-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="78a89-160">Дополнительные сведения и примеры см. в разделах [Практическое руководство. Использование именованных и необязательных аргументов в программировании Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) и [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="78a89-160">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="78a89-161">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="78a89-161">Overload Resolution</span></span>  
 <span data-ttu-id="78a89-162">Использование именованных и необязательных аргументов влияет на разрешение перегрузки описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="78a89-162">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="78a89-163">Метод, индексатор или конструктор является кандидатом на выполнение, если каждый из его параметров необязателен либо по имени или позиции соответствует одному и тому же аргументу в операторе вызова, и этот аргумент можно преобразовать в тип параметра.</span><span class="sxs-lookup"><span data-stu-id="78a89-163">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="78a89-164">Если найдено более одного кандидата, правила разрешения перегрузки для предпочтительных преобразований применяются к аргументам, указанным явно.</span><span class="sxs-lookup"><span data-stu-id="78a89-164">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="78a89-165">Опущенные аргументы для необязательных параметров игнорируются.</span><span class="sxs-lookup"><span data-stu-id="78a89-165">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="78a89-166">Если два кандидата определяются как равно подходящие, предпочтение отдается кандидату без необязательных параметров, аргументы которых в вызове были опущены.</span><span class="sxs-lookup"><span data-stu-id="78a89-166">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="78a89-167">Это — последовательность определения приоритетов в разрешении перегрузки для кандидатов с меньшим числом параметров.</span><span class="sxs-lookup"><span data-stu-id="78a89-167">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="78a89-168">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="78a89-168">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78a89-169">См. также</span><span class="sxs-lookup"><span data-stu-id="78a89-169">See Also</span></span>  
 <span data-ttu-id="78a89-170">[Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="78a89-170">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="78a89-171">[Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="78a89-171">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="78a89-172">[Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="78a89-172">[Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span></span>  
 [<span data-ttu-id="78a89-173">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="78a89-173">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)

