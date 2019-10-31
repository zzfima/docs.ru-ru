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
ms.openlocfilehash: 83e465651762fce33a62009fb3add40373a33c51
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772127"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="07e6a-102">Именованные и необязательные аргументы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="07e6a-102">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="07e6a-103">C# 4 вводит именованные и необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="07e6a-103">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="07e6a-104">*Именованные аргументы* позволяют указать аргумент для определенного параметра, связав этот аргумент с именем параметра, а не с его позицией в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="07e6a-105">*Необязательные аргументы* позволяют опускать аргументы для некоторых параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="07e6a-106">Оба варианта можно использовать с методами, индексаторами, конструкторами и делегатами.</span><span class="sxs-lookup"><span data-stu-id="07e6a-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="07e6a-107">При использовании именованных и необязательных аргументов аргументы оцениваются в том порядке, в котором они отображаются в списке аргументов, а не в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="07e6a-108">При совместном использовании именованные и необязательные параметры позволяют задавать аргументы только для некоторых параметров из списка необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="07e6a-109">Эта возможность значительно упрощает вызов интерфейсов COM, таких как API автоматизации Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="07e6a-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="07e6a-110">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="07e6a-110">Named Arguments</span></span>  
 <span data-ttu-id="07e6a-111">Именованные аргументы освобождают разработчика от необходимости запоминать или уточнять порядок параметров в списках параметров вызванных методов.</span><span class="sxs-lookup"><span data-stu-id="07e6a-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="07e6a-112">Параметр для каждого аргумента можно указать, используя имя параметра.</span><span class="sxs-lookup"><span data-stu-id="07e6a-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="07e6a-113">Например, функция, которая выводит сведения о заказе (например, имя продавца, номер заказа и наименование товара), может вызываться как обычно, путем передачи аргументов по позиции в порядке, определяемом функцией.</span><span class="sxs-lookup"><span data-stu-id="07e6a-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="07e6a-114">Если вы не помните порядок параметров, но знаете их имена, можете передать аргументы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="07e6a-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="07e6a-115">Именованные аргументы также делают код более удобным для чтения, поскольку указывают, чему соответствует каждый аргумент.</span><span class="sxs-lookup"><span data-stu-id="07e6a-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="07e6a-116">В приведенном ниже примере метода `sellerName` не может быть равен NULL или пробелу.</span><span class="sxs-lookup"><span data-stu-id="07e6a-116">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="07e6a-117">Так как и `sellerName`, и `productName` являются строковыми типами, вместо передачи аргументов по позиции имеет смысл использовать именованные аргументы, чтобы устранить данную неоднозначность и сделать код более удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="07e6a-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="07e6a-118">Именованные аргументы при использовании с позиционными аргументами допустимы при условии, что</span><span class="sxs-lookup"><span data-stu-id="07e6a-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="07e6a-119">за ними не следуют позиционные аргументы, либо,</span><span class="sxs-lookup"><span data-stu-id="07e6a-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="07e6a-120">_начиная с C# 7.2_, они используются в правильной позиции.</span><span class="sxs-lookup"><span data-stu-id="07e6a-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="07e6a-121">В примере ниже параметр `orderNum` находится в правильной позиции, но не имеет явно заданного имени.</span><span class="sxs-lookup"><span data-stu-id="07e6a-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="07e6a-122">Позиционные аргументы после внеочередных именованных аргументов недопустимы.</span><span class="sxs-lookup"><span data-stu-id="07e6a-122">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="07e6a-123">Пример</span><span class="sxs-lookup"><span data-stu-id="07e6a-123">Example</span></span>  
 <span data-ttu-id="07e6a-124">Приведенный ниже код реализует как примеры из этого раздела, так и некоторые дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="07e6a-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="07e6a-125">Необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="07e6a-125">Optional Arguments</span></span>  
 <span data-ttu-id="07e6a-126">Определение метода, конструктора, индексатора или делегата может указывать, являются его параметры обязательными или нет.</span><span class="sxs-lookup"><span data-stu-id="07e6a-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="07e6a-127">Любой вызов должен содержать аргументы для всех обязательных параметров; аргументы для необязательных параметров можно опустить.</span><span class="sxs-lookup"><span data-stu-id="07e6a-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="07e6a-128">Определение каждого необязательного параметра содержит его значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07e6a-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="07e6a-129">Если аргумент для параметра не передается, используется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07e6a-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="07e6a-130">Значением по умолчанию должен быть один из следующих типов выражений:</span><span class="sxs-lookup"><span data-stu-id="07e6a-130">A default value must be one of the following types of expressions:</span></span>  
  
- <span data-ttu-id="07e6a-131">константное выражение;</span><span class="sxs-lookup"><span data-stu-id="07e6a-131">a constant expression;</span></span>  
  
- <span data-ttu-id="07e6a-132">выражение в форме `new ValType()`, где `ValType` — это тип значения, например, [enum](../../language-reference/keywords/enum.md) или [struct](./structs.md);</span><span class="sxs-lookup"><span data-stu-id="07e6a-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/keywords/enum.md) or a [struct](./structs.md);</span></span>  
  
- <span data-ttu-id="07e6a-133">выражение в форме [default(ValType)](../../language-reference/operators/default.md), где `ValType` — это тип значения.</span><span class="sxs-lookup"><span data-stu-id="07e6a-133">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="07e6a-134">Необязательные параметры определяются в конце списка параметров после всех обязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="07e6a-135">Если вызывающий объект предоставляет аргумент для любого из последующих необязательных параметров, он должен содержать аргументы для всех предыдущих необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="07e6a-136">Пробелы, разделенные запятыми, в списке аргументов не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="07e6a-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="07e6a-137">Например, в следующем коде метод экземпляра `ExampleMethod` определяется одним обязательным и двумя необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="07e6a-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 <span data-ttu-id="07e6a-138">Следующий вызов `ExampleMethod` вызывает ошибку компилятора, поскольку аргумент предоставляется для третьего параметра, но не для второго.</span><span class="sxs-lookup"><span data-stu-id="07e6a-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="07e6a-139">Если вы знаете имя третьего параметра, можете использовать для выполнения задачи именованный аргумент.</span><span class="sxs-lookup"><span data-stu-id="07e6a-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="07e6a-140">В IntelliSense необязательные параметры заключаются в квадратные скобки, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="07e6a-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>  
  
 ![Снимок экрана, показывающий краткие сведения IntelliSense для метода ExampleMethod.](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> <span data-ttu-id="07e6a-142">Необязательные параметры также можно объявлять с помощью класса .NET <xref:System.Runtime.InteropServices.OptionalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="07e6a-142">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="07e6a-143">Для параметров `OptionalAttribute` значение по умолчанию не требуется.</span><span class="sxs-lookup"><span data-stu-id="07e6a-143">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07e6a-144">Пример</span><span class="sxs-lookup"><span data-stu-id="07e6a-144">Example</span></span>  
 <span data-ttu-id="07e6a-145">В следующем примере конструктор `ExampleClass` имеет один параметр, который является необязательным.</span><span class="sxs-lookup"><span data-stu-id="07e6a-145">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="07e6a-146">У метода экземпляра `ExampleMethod` есть один обязательный параметр, `required`, и два необязательных параметра, `optionalstr` и `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="07e6a-146">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="07e6a-147">Код в `Main` демонстрирует различные способы, которые можно использовать для вызова конструктора и метода.</span><span class="sxs-lookup"><span data-stu-id="07e6a-147">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="07e6a-148">Интерфейсы COM</span><span class="sxs-lookup"><span data-stu-id="07e6a-148">COM Interfaces</span></span>  
 <span data-ttu-id="07e6a-149">Именованные и необязательные аргументы, а также поддержка динамических объектов и другие усовершенствования значительно улучшают взаимодействие с API COM, такими как API автоматизации Office.</span><span class="sxs-lookup"><span data-stu-id="07e6a-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="07e6a-150">Например, метод <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A>в интерфейсе Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> имеет семь параметров и все они необязательные.</span><span class="sxs-lookup"><span data-stu-id="07e6a-150">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="07e6a-151">Эти параметры показаны на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="07e6a-151">These parameters are shown in the following illustration:</span></span>  
  
 ![Снимок экрана, показывающий краткие сведения IntelliSense для метода AutoFormat.](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 <span data-ttu-id="07e6a-153">В C# 3.0 и более ранних версиях аргумент необходимо указывать для каждого параметра, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="07e6a-153">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 <span data-ttu-id="07e6a-154">При этом вызов `AutoFormat` можно значительно упростить, используя именованные и необязательные аргументы, представленные в C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="07e6a-154">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="07e6a-155">Именованные и необязательные аргументы позволяют опускать аргументы для необязательных параметров, если значение параметра по умолчанию менять не нужно.</span><span class="sxs-lookup"><span data-stu-id="07e6a-155">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="07e6a-156">В следующем вызове значение задается только для одного из семи параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-156">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 <span data-ttu-id="07e6a-157">Дополнительные сведения и примеры см. в статьях [Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](./how-to-use-named-and-optional-arguments-in-office-programming.md) и [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций Visual C#](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="07e6a-157">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="07e6a-158">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="07e6a-158">Overload Resolution</span></span>  
 <span data-ttu-id="07e6a-159">Использование именованных и необязательных аргументов влияет на разрешение перегрузки описанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="07e6a-159">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
- <span data-ttu-id="07e6a-160">Метод, индексатор или конструктор является кандидатом на выполнение, если каждый из его параметров необязателен либо по имени или позиции соответствует одному и тому же аргументу в операторе вызова, и этот аргумент можно преобразовать в тип параметра.</span><span class="sxs-lookup"><span data-stu-id="07e6a-160">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
- <span data-ttu-id="07e6a-161">Если найдено более одного кандидата, правила разрешения перегрузки для предпочтительных преобразований применяются к аргументам, указанным явно.</span><span class="sxs-lookup"><span data-stu-id="07e6a-161">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="07e6a-162">Опущенные аргументы для необязательных параметров игнорируются.</span><span class="sxs-lookup"><span data-stu-id="07e6a-162">Omitted arguments for optional parameters are ignored.</span></span>  
  
- <span data-ttu-id="07e6a-163">Если два кандидата определяются как равно подходящие, предпочтение отдается кандидату без необязательных параметров, аргументы которых в вызове были опущены.</span><span class="sxs-lookup"><span data-stu-id="07e6a-163">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="07e6a-164">Это — последовательность определения приоритетов в разрешении перегрузки для кандидатов с меньшим числом параметров.</span><span class="sxs-lookup"><span data-stu-id="07e6a-164">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="07e6a-165">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="07e6a-165">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07e6a-166">См. также</span><span class="sxs-lookup"><span data-stu-id="07e6a-166">See also</span></span>

- [<span data-ttu-id="07e6a-167">Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office</span><span class="sxs-lookup"><span data-stu-id="07e6a-167">How to: Use Named and Optional Arguments in Office Programming</span></span>](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="07e6a-168">Использование типа dynamic</span><span class="sxs-lookup"><span data-stu-id="07e6a-168">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="07e6a-169">Использование конструкторов</span><span class="sxs-lookup"><span data-stu-id="07e6a-169">Using Constructors</span></span>](./using-constructors.md)
- [<span data-ttu-id="07e6a-170">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="07e6a-170">Using Indexers</span></span>](../indexers/using-indexers.md)
