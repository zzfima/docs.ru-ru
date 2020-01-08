---
title: Разработка параметров
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: 93554594b49b742a6a5e8461b6b16046701ec07c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347853"
---
# <a name="parameter-design"></a><span data-ttu-id="60af3-102">Конструктор параметров</span><span class="sxs-lookup"><span data-stu-id="60af3-102">Parameter design</span></span>

<span data-ttu-id="60af3-103">В этом разделе приводятся общие рекомендации по проектированию параметров, включая разделы с рекомендациями по проверке аргументов.</span><span class="sxs-lookup"><span data-stu-id="60af3-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="60af3-104">Кроме того, следует ознакомиться с рекомендациями, описанными в разделе [параметры именования](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="60af3-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="60af3-105">**✓ DO** использовать бы производный тип параметра, который предоставляет функциональные возможности, необходимые для элемента.</span><span class="sxs-lookup"><span data-stu-id="60af3-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="60af3-106">Например, предположим, что требуется разработать метод, который перечисляет коллекцию и выводит каждый элемент на консоль.</span><span class="sxs-lookup"><span data-stu-id="60af3-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="60af3-107">Такой метод должен принимать <xref:System.Collections.IEnumerable> в качестве параметра, а не <xref:System.Collections.ArrayList> или <xref:System.Collections.IList>, например.</span><span class="sxs-lookup"><span data-stu-id="60af3-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="60af3-108">**X DO NOT** использовать зарезервированные параметры.</span><span class="sxs-lookup"><span data-stu-id="60af3-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="60af3-109">Если в какой-либо будущей версии требуется больше входных данных для члена, можно добавить новую перегрузку.</span><span class="sxs-lookup"><span data-stu-id="60af3-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="60af3-110">**X DO NOT** открытым методы, принимающие указатели, массивы указателей или многомерных массивов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="60af3-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="60af3-111">Указатели и многомерные массивы относительно сложно правильно использовать.</span><span class="sxs-lookup"><span data-stu-id="60af3-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="60af3-112">В большинстве случаев можно перерабатывать API, чтобы избежать использования этих типов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="60af3-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="60af3-113">**✓ DO** поместите все `out` параметров после всех по значению и `ref` параметров (за исключением массивы параметров), даже если это приводит к несогласованность параметров перегрузки в (см. [члена Перегрузка](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="60af3-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="60af3-114">Параметры `out` могут рассматриваться как дополнительные возвращаемые значения, и их группирование позволяет проще понять сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="60af3-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="60af3-115">**✓ DO** быть согласованы в именовании параметров при перегрузке членов или реализации интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="60af3-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="60af3-116">Это улучшает связь между методами.</span><span class="sxs-lookup"><span data-stu-id="60af3-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choose-between-enum-and-boolean-parameters"></a><span data-ttu-id="60af3-117">Выбор между перечислением и логическими параметрами</span><span class="sxs-lookup"><span data-stu-id="60af3-117">Choose between enum and boolean parameters</span></span>  
 <span data-ttu-id="60af3-118">**✓ DO** использовать перечисления, если член будет иметь два или более логических параметров.</span><span class="sxs-lookup"><span data-stu-id="60af3-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="60af3-119">**X DO NOT** используйте логические значения, пока не будет точно знать, никогда не возникнет необходимость использования более двух значений.</span><span class="sxs-lookup"><span data-stu-id="60af3-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="60af3-120">Перечисления предоставляют некоторое место для добавления значений в будущем, но следует помнить о всех последствиях добавления значений к перечислениям, которые описаны в статье о [структуре перечисления](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="60af3-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="60af3-121">**✓ CONSIDER** с помощью логических значений для параметров конструктора, действительно два значения состояния и используются исключительно для инициализации свойства типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="60af3-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validate-arguments"></a><span data-ttu-id="60af3-122">Проверить аргументы</span><span class="sxs-lookup"><span data-stu-id="60af3-122">Validate arguments</span></span>  
 <span data-ttu-id="60af3-123">**✓ DO** проверить аргументы, передаваемые открытый, защищенный или явно реализованный членов.</span><span class="sxs-lookup"><span data-stu-id="60af3-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="60af3-124">Вызовите <xref:System.ArgumentException?displayProperty=nameWithType>или один из его подклассов, если проверка завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="60af3-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="60af3-125">Обратите внимание, что фактическая проверка не обязательно должна выполняться в самом открытом или защищенном члене.</span><span class="sxs-lookup"><span data-stu-id="60af3-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="60af3-126">Это может произойти на более низком уровне в некоторых частных или внутренних подпрограммых.</span><span class="sxs-lookup"><span data-stu-id="60af3-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="60af3-127">Главным моментом является то, что вся контактная зона, предоставляемая конечным пользователям, проверяет аргументы.</span><span class="sxs-lookup"><span data-stu-id="60af3-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="60af3-128">**✓ DO** throw <xref:System.ArgumentNullException> Если передается аргумент null и элемент не поддерживает аргументы null.</span><span class="sxs-lookup"><span data-stu-id="60af3-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="60af3-129">**✓ DO** проверки для параметров перечислений.</span><span class="sxs-lookup"><span data-stu-id="60af3-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="60af3-130">Не представим, что аргументы перечисления будут находиться в диапазоне, определенном перечислением.</span><span class="sxs-lookup"><span data-stu-id="60af3-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="60af3-131">Среда CLR позволяет приведение любого целочисленного значения к значению перечисления, даже если оно не определено в перечислении.</span><span class="sxs-lookup"><span data-stu-id="60af3-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="60af3-132">**X DO NOT** использовать <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> диапазона перечисления проверяет.</span><span class="sxs-lookup"><span data-stu-id="60af3-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="60af3-133">**✓ DO** Имейте в виду, что изменяемые аргументы могут были изменены после они были проверены.</span><span class="sxs-lookup"><span data-stu-id="60af3-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="60af3-134">Если элемент защищен с учетом безопасности, рекомендуется создать копию, а затем проверить и обработать аргумент.</span><span class="sxs-lookup"><span data-stu-id="60af3-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="pass-parameters"></a><span data-ttu-id="60af3-135">Передача параметров</span><span class="sxs-lookup"><span data-stu-id="60af3-135">Pass parameters</span></span>  
 <span data-ttu-id="60af3-136">С точки зрения конструктора инфраструктуры существуют три основные группы параметров: параметры по значению, параметры `ref` и параметры `out`.</span><span class="sxs-lookup"><span data-stu-id="60af3-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="60af3-137">Когда аргумент передается через параметр по значению, член получает копию фактического аргумента, переданного в.</span><span class="sxs-lookup"><span data-stu-id="60af3-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="60af3-138">Если аргумент является типом значения, в стек помещается копия аргумента.</span><span class="sxs-lookup"><span data-stu-id="60af3-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="60af3-139">Если аргумент является ссылочным типом, в стек помещается копия ссылки.</span><span class="sxs-lookup"><span data-stu-id="60af3-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="60af3-140">Наиболее популярные языки CLR, такие как C#, Visual Basic и C++, по умолчанию передают параметры по значению.</span><span class="sxs-lookup"><span data-stu-id="60af3-140">Most popular CLR languages, such as C#, Visual Basic, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="60af3-141">Когда аргумент передается через параметр `ref`, член получает ссылку на фактический аргумент, переданный в.</span><span class="sxs-lookup"><span data-stu-id="60af3-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="60af3-142">Если аргумент является типом значения, в стек помещается ссылка на аргумент.</span><span class="sxs-lookup"><span data-stu-id="60af3-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="60af3-143">Если аргумент является ссылочным типом, ссылка на ссылку помещается в стек.</span><span class="sxs-lookup"><span data-stu-id="60af3-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="60af3-144">`Ref` параметры можно использовать, чтобы разрешить члену изменять аргументы, передаваемые вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="60af3-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="60af3-145">Параметры `Out` похожи на параметры `ref` и некоторые небольшие различия.</span><span class="sxs-lookup"><span data-stu-id="60af3-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="60af3-146">Параметр изначально считается неназначенным и не может быть прочитан в теле элемента до того, как ему будет присвоено какое-либо значение.</span><span class="sxs-lookup"><span data-stu-id="60af3-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="60af3-147">Кроме того, параметру необходимо назначить некоторое значение перед возвратом члена.</span><span class="sxs-lookup"><span data-stu-id="60af3-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="60af3-148">**X AVOID** с помощью `out` или `ref` параметров.</span><span class="sxs-lookup"><span data-stu-id="60af3-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="60af3-149">Для использования параметров `out` или `ref` требуется взаимодействие с указателями, понимание того, как типы значений и ссылочные типы различаются, и обрабатывает методы с несколькими возвращаемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="60af3-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="60af3-150">Кроме того, различие между параметрами `out` и `ref` не является широко понятным.</span><span class="sxs-lookup"><span data-stu-id="60af3-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="60af3-151">Архитекторы платформ, разрабатываемые для общей аудитории, не должны ждать, чтобы пользователи работали с `out` или `ref` параметрами.</span><span class="sxs-lookup"><span data-stu-id="60af3-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="60af3-152">**X DO NOT** передачи ссылочных типов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="60af3-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="60af3-153">Существует несколько ограниченных исключений правила, например метод, который может использоваться для замены ссылок.</span><span class="sxs-lookup"><span data-stu-id="60af3-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="60af3-154">Члены с переменным числом параметров</span><span class="sxs-lookup"><span data-stu-id="60af3-154">Members with variable number of parameters</span></span>  
 <span data-ttu-id="60af3-155">Члены, которые могут принимать переменное число аргументов, выражаются путем предоставления параметра массива.</span><span class="sxs-lookup"><span data-stu-id="60af3-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="60af3-156">Например, <xref:System.String> предоставляет следующий метод:</span><span class="sxs-lookup"><span data-stu-id="60af3-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```csharp  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="60af3-157">Затем пользователь может вызвать метод <xref:System.String.Format%2A?displayProperty=nameWithType> следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60af3-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="60af3-158">Добавление ключевого слова C# params в параметр массива приводит к изменению параметра на так называемый параметр массива params и предоставляет ярлык для создания временного массива.</span><span class="sxs-lookup"><span data-stu-id="60af3-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```csharp  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="60af3-159">Это позволяет пользователю вызывать метод, передавая элементы массива непосредственно в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="60af3-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="60af3-160">Обратите внимание, что ключевое слово params можно добавить только к последнему параметру в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="60af3-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="60af3-161">**✓ CONSIDER** Добавление ключевого слова params параметров массива, если ожидается, что конечных пользователей для передачи массивов с небольшим числом элементов.</span><span class="sxs-lookup"><span data-stu-id="60af3-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="60af3-162">Если предполагается, что множество элементов будет передаваться в типичных сценариях, пользователи, вероятно, не будут передавать эти элементы в любом случае, поэтому ключевое слово params не требуется.</span><span class="sxs-lookup"><span data-stu-id="60af3-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="60af3-163">**X AVOID** использование массивов params в том случае, если вызывающий объект будет почти всегда уже входные данные в виде массива.</span><span class="sxs-lookup"><span data-stu-id="60af3-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="60af3-164">Например, члены с параметрами массива байтов почти никогда не вызываются путем передачи отдельных байтов.</span><span class="sxs-lookup"><span data-stu-id="60af3-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="60af3-165">По этой причине параметры массива байтов в .NET Framework не используют ключевое слово params.</span><span class="sxs-lookup"><span data-stu-id="60af3-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="60af3-166">**X DO NOT** используйте массивы params, если массив изменен членом, принимающим параметр params массива.</span><span class="sxs-lookup"><span data-stu-id="60af3-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="60af3-167">Из-за того, что многие компиляторы переключают аргументы в временный массив в месте вызова, массив может быть временным объектом, поэтому любые изменения массива будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="60af3-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="60af3-168">**✓ CONSIDER** с помощью ключевого слова params в простой перегрузке, даже если более сложная перегрузка не может использовать его.</span><span class="sxs-lookup"><span data-stu-id="60af3-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="60af3-169">Задайте себе, если бы пользователь мог бы получить значение массива params в одной перегрузке, даже если это не было во всех перегрузках.</span><span class="sxs-lookup"><span data-stu-id="60af3-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="60af3-170">**✓ DO** попытайтесь Упорядочить параметры, чтобы сделать возможным использование ключевого слова params.</span><span class="sxs-lookup"><span data-stu-id="60af3-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="60af3-171">**✓ CONSIDER** предусматривать особые перегрузки и ветви кода для вызовов с небольшим числом аргументов в API-интерфейсы важна высокая производительность.</span><span class="sxs-lookup"><span data-stu-id="60af3-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="60af3-172">Это позволяет избежать создания объектов Array при вызове API с небольшим числом аргументов.</span><span class="sxs-lookup"><span data-stu-id="60af3-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="60af3-173">Произведение имен параметров путем создания единственного значения параметра массива и добавления числового суффикса.</span><span class="sxs-lookup"><span data-stu-id="60af3-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="60af3-174">Это следует делать только в том случае, если вы собираетесь использовать весь путь к коду, а не просто создаете массив и вызываете более общий метод.</span><span class="sxs-lookup"><span data-stu-id="60af3-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="60af3-175">**✓ DO** Имейте в виду, null может быть передан в качестве аргумента массива params.</span><span class="sxs-lookup"><span data-stu-id="60af3-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="60af3-176">Перед обработкой необходимо проверить, что массив не равен null.</span><span class="sxs-lookup"><span data-stu-id="60af3-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="60af3-177">**X DO NOT** использовать `varargs` методы, также известный как кнопку с многоточием.</span><span class="sxs-lookup"><span data-stu-id="60af3-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="60af3-178">Некоторые языки CLR, такие как C++, поддерживают альтернативное соглашение для передачи списков параметров переменных, именуемых `varargs` методами.</span><span class="sxs-lookup"><span data-stu-id="60af3-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="60af3-179">Это соглашение не должно использоваться в платформах, поскольку оно несовместимо с CLS.</span><span class="sxs-lookup"><span data-stu-id="60af3-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="60af3-180">Параметры указателя</span><span class="sxs-lookup"><span data-stu-id="60af3-180">Pointer parameters</span></span>  
 <span data-ttu-id="60af3-181">Как правило, указатели не должны отображаться в общедоступной контактной зоне хорошо спроектированной инфраструктуры управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="60af3-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="60af3-182">В большинстве случаев указатели должны быть инкапсулированы.</span><span class="sxs-lookup"><span data-stu-id="60af3-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="60af3-183">Однако в некоторых случаях указатели необходимы для обеспечения взаимодействия, и использование указателей в таких случаях уместно.</span><span class="sxs-lookup"><span data-stu-id="60af3-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="60af3-184">**✓ DO** предоставляют альтернативный для любого элемента, который принимает указатель в качестве аргумента, так как указатели не являются CLS-совместимыми.</span><span class="sxs-lookup"><span data-stu-id="60af3-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="60af3-185">**X AVOID** затратного контроля аргументов указатель аргументов.</span><span class="sxs-lookup"><span data-stu-id="60af3-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="60af3-186">**✓ DO** соглашениям общих указателей при разработке члены с указателями.</span><span class="sxs-lookup"><span data-stu-id="60af3-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="60af3-187">Например, нет необходимости передавать начальный индекс, так как для достижения того же результата можно использовать простые арифметические операции с указателями.</span><span class="sxs-lookup"><span data-stu-id="60af3-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="60af3-188">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="60af3-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="60af3-189">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="60af3-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60af3-190">См. также:</span><span class="sxs-lookup"><span data-stu-id="60af3-190">See also</span></span>

- [<span data-ttu-id="60af3-191">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="60af3-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="60af3-192">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="60af3-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
