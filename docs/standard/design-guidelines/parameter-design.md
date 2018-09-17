---
title: Разработка параметров
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5311de8cef266af23b259d943568bfa95eaf72
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964820"
---
# <a name="parameter-design"></a><span data-ttu-id="8a52d-102">Разработка параметров</span><span class="sxs-lookup"><span data-stu-id="8a52d-102">Parameter Design</span></span>
<span data-ttu-id="8a52d-103">Этот раздел содержит общие рекомендации по разработке параметров, включая разделы с рекомендации по проверке аргументов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="8a52d-104">Кроме того, следует ознакомиться с рекомендации, приведенные в [именования параметров](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8a52d-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="8a52d-105">**✓ DO** использовать бы производный тип параметра, который предоставляет функциональные возможности, необходимые для элемента.</span><span class="sxs-lookup"><span data-stu-id="8a52d-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="8a52d-106">Например предположим, что необходимо разработать метод, который перечисляет коллекцию и печатает каждый элемент в консоль.</span><span class="sxs-lookup"><span data-stu-id="8a52d-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="8a52d-107">Такой метод должен принимать <xref:System.Collections.IEnumerable> как параметр, не <xref:System.Collections.ArrayList> или <xref:System.Collections.IList>, например.</span><span class="sxs-lookup"><span data-stu-id="8a52d-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="8a52d-108">**X DO NOT** использовать зарезервированные параметры.</span><span class="sxs-lookup"><span data-stu-id="8a52d-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="8a52d-109">Если в одной из последующих версий необходимо дополнительные входные данные для члена, могут добавляться новая перегрузка.</span><span class="sxs-lookup"><span data-stu-id="8a52d-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="8a52d-110">**X DO NOT** открытым методы, принимающие указатели, массивы указателей или многомерных массивов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="8a52d-111">Указатели и многомерные массивы являются довольно сложно использовать правильно.</span><span class="sxs-lookup"><span data-stu-id="8a52d-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="8a52d-112">Практически во всех случаях API-интерфейсов может быть переработано избежать этих типов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="8a52d-113">**✓ DO** поместите все `out` параметров после всех по значению и `ref` параметров (за исключением массивы параметров), даже если это приводит к несогласованность параметров перегрузки в (см. [члена Перегрузка](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="8a52d-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="8a52d-114">`out` Параметры можно рассматривать как очень возвращаемые значения и сгруппировать их метод подпись становится легче понять.</span><span class="sxs-lookup"><span data-stu-id="8a52d-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="8a52d-115">**✓ DO** быть согласованы в именовании параметров при перегрузке членов или реализации интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="8a52d-116">Это лучше взаимодействует связь между этими методами.</span><span class="sxs-lookup"><span data-stu-id="8a52d-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="8a52d-117">Выбор между Enum и логических параметров</span><span class="sxs-lookup"><span data-stu-id="8a52d-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="8a52d-118">**✓ DO** использовать перечисления, если член будет иметь два или более логических параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="8a52d-119">**X DO NOT** используйте логические значения, пока не будет точно знать, никогда не возникнет необходимость использования более двух значений.</span><span class="sxs-lookup"><span data-stu-id="8a52d-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="8a52d-120">Перечисления предоставляют некоторый запас будущих сложение значений, но следует иметь в виду возможное влияние добавления значения перечислений, которые описаны в [Разработка перечислений](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="8a52d-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="8a52d-121">**✓ CONSIDER** с помощью логических значений для параметров конструктора, действительно два значения состояния и используются исключительно для инициализации свойства типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="8a52d-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="8a52d-122">Проверка аргументов</span><span class="sxs-lookup"><span data-stu-id="8a52d-122">Validating Arguments</span></span>  
 <span data-ttu-id="8a52d-123">**✓ DO** проверить аргументы, передаваемые открытый, защищенный или явно реализованный членов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="8a52d-124">Исключение <xref:System.ArgumentException?displayProperty=nameWithType>, или одного из его подклассов, если проверка не пройдена.</span><span class="sxs-lookup"><span data-stu-id="8a52d-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="8a52d-125">Обратите внимание, что фактическая проверка не обязательно должна производиться в сам открытый или защищенный элемент.</span><span class="sxs-lookup"><span data-stu-id="8a52d-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="8a52d-126">Может произойти на более низком уровне в подпрограмме некоторые закрытым или внутренним.</span><span class="sxs-lookup"><span data-stu-id="8a52d-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="8a52d-127">Самое главное, что всей контактной зоной, предоставляемая конечным пользователям проверяет аргументы.</span><span class="sxs-lookup"><span data-stu-id="8a52d-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="8a52d-128">**✓ DO** throw <xref:System.ArgumentNullException> Если передается аргумент null и элемент не поддерживает аргументы null.</span><span class="sxs-lookup"><span data-stu-id="8a52d-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="8a52d-129">**✓ DO** проверки для параметров перечислений.</span><span class="sxs-lookup"><span data-stu-id="8a52d-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="8a52d-130">Не считайте, что аргументы enum будет находиться в диапазоне, определяемых перечислением.</span><span class="sxs-lookup"><span data-stu-id="8a52d-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="8a52d-131">Среда CLR позволяет приведение любого целого числа в значение перечисления, даже если значение не определено в перечислении.</span><span class="sxs-lookup"><span data-stu-id="8a52d-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="8a52d-132">**X DO NOT** использовать <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> диапазона перечисления проверяет.</span><span class="sxs-lookup"><span data-stu-id="8a52d-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="8a52d-133">**✓ DO** Имейте в виду, что изменяемые аргументы могут были изменены после они были проверены.</span><span class="sxs-lookup"><span data-stu-id="8a52d-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="8a52d-134">Если член является влияет на безопасность, вы, рекомендуется создать копию, а затем проверить и обработать аргумент.</span><span class="sxs-lookup"><span data-stu-id="8a52d-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="8a52d-135">Передача параметров</span><span class="sxs-lookup"><span data-stu-id="8a52d-135">Parameter Passing</span></span>  
 <span data-ttu-id="8a52d-136">С точки зрения конструктор framework, существует три основных группы параметров: параметры, по значению `ref` параметров, и `out` параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="8a52d-137">Если аргумент, передаваемый в качестве параметра по значению, член получает копию фактического аргумента, переданного в.</span><span class="sxs-lookup"><span data-stu-id="8a52d-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="8a52d-138">Если аргумент является типом значения, копию аргумента помещается в стек.</span><span class="sxs-lookup"><span data-stu-id="8a52d-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="8a52d-139">Если аргумент является ссылочным типом, копии ссылки помещается в стек.</span><span class="sxs-lookup"><span data-stu-id="8a52d-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="8a52d-140">Наиболее популярных языков среды CLR, таких как C#, VB.NET и C++, по умолчанию для передачи параметров по значению.</span><span class="sxs-lookup"><span data-stu-id="8a52d-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="8a52d-141">Если аргумент, передаваемый через `ref` параметра, члена получает ссылку на фактический аргумент, передаваемый в.</span><span class="sxs-lookup"><span data-stu-id="8a52d-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="8a52d-142">Если аргумент является типом значения, ссылка на аргумент помещается в стек.</span><span class="sxs-lookup"><span data-stu-id="8a52d-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="8a52d-143">Если аргумент является ссылочным типом, ссылку на ссылку помещается в стек.</span><span class="sxs-lookup"><span data-stu-id="8a52d-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="8a52d-144">`Ref` параметры могут использоваться, элемент изменить аргументы, передаваемые в вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="8a52d-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="8a52d-145">`Out` параметры аналогичны `ref` параметров, некоторые небольшие различия.</span><span class="sxs-lookup"><span data-stu-id="8a52d-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="8a52d-146">Параметр считается изначально неназначенных и не удается прочитать в теле элемента перед его присваиванием некоторое значение.</span><span class="sxs-lookup"><span data-stu-id="8a52d-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="8a52d-147">Кроме того параметр должен быть назначен некоторое значение, прежде чем элемент возвращает.</span><span class="sxs-lookup"><span data-stu-id="8a52d-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="8a52d-148">**X AVOID** с помощью `out` или `ref` параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="8a52d-149">С помощью `out` или `ref` параметров требуется опыт работы с указателями, понимание отличия между типами значения и ссылочными типами и умение работать с методами с несколькими возвращаемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="8a52d-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="8a52d-150">Кроме того, разница между `out` и `ref` параметров не все понимают.</span><span class="sxs-lookup"><span data-stu-id="8a52d-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="8a52d-151">Архитекторы Framework, разработке для широкого использования не должен ожидать пользователям разрабатывающим `out` или `ref` параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="8a52d-152">**X DO NOT** передачи ссылочных типов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="8a52d-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="8a52d-153">Существует несколько исключений для правила, например метод, который может использоваться для замены ссылок.</span><span class="sxs-lookup"><span data-stu-id="8a52d-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="8a52d-154">Члены с переменным числом параметров</span><span class="sxs-lookup"><span data-stu-id="8a52d-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="8a52d-155">Члены, которые могут принимать переменное число аргументов выражаются, предоставляя параметр массива.</span><span class="sxs-lookup"><span data-stu-id="8a52d-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="8a52d-156">Например <xref:System.String> предоставляет следующий метод:</span><span class="sxs-lookup"><span data-stu-id="8a52d-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="8a52d-157">Пользователь может затем вызвать <xref:System.String.Format%2A?displayProperty=nameWithType> метода, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="8a52d-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="8a52d-158">Добавление ключевого слова C# params к параметру массива изменяет параметр к параметру массива так называемые params и сочетание клавиш для создания временного массива.</span><span class="sxs-lookup"><span data-stu-id="8a52d-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="8a52d-159">Это позволяет вызывать метод, передав элементы массива непосредственно в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="8a52d-160">Обратите внимание, что ключевое слово params могут добавляться только к последнему параметру в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="8a52d-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="8a52d-161">**✓ CONSIDER** Добавление ключевого слова params параметров массива, если ожидается, что конечных пользователей для передачи массивов с небольшим числом элементов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="8a52d-162">Если предполагается, что большое количество элементов будут передаваться в распространенных сценариях, пользователи скорее всего, не будет передавать эти встроенные элементы в любом случае, и ключевого слова params не требуется.</span><span class="sxs-lookup"><span data-stu-id="8a52d-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="8a52d-163">**X AVOID** использование массивов params в том случае, если вызывающий объект будет почти всегда уже входные данные в виде массива.</span><span class="sxs-lookup"><span data-stu-id="8a52d-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="8a52d-164">Например элементы с помощью параметров-массивов байтов практически никогда не будет называться путем передачи отдельных байтов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="8a52d-165">По этой причине параметров массива байтов в .NET Framework не используйте ключевое слово params.</span><span class="sxs-lookup"><span data-stu-id="8a52d-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="8a52d-166">**X DO NOT** используйте массивы params, если массив изменен членом, принимающим параметр params массива.</span><span class="sxs-lookup"><span data-stu-id="8a52d-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="8a52d-167">Из-за того, что многие компилятор преобразует аргументы в элемент во временный массив во время вызова массив может быть временным объектом, и таким образом будут потеряны все изменения в массив.</span><span class="sxs-lookup"><span data-stu-id="8a52d-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="8a52d-168">**✓ CONSIDER** с помощью ключевого слова params в простой перегрузке, даже если более сложная перегрузка не может использовать его.</span><span class="sxs-lookup"><span data-stu-id="8a52d-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="8a52d-169">Спросите себя, если бы значение для пользователей с массивом параметров в одной перегрузке, даже если он не был в все перегрузки.</span><span class="sxs-lookup"><span data-stu-id="8a52d-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="8a52d-170">**✓ DO** попытайтесь Упорядочить параметры, чтобы сделать возможным использование ключевого слова params.</span><span class="sxs-lookup"><span data-stu-id="8a52d-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="8a52d-171">**✓ CONSIDER** предусматривать особые перегрузки и ветви кода для вызовов с небольшим числом аргументов в API-интерфейсы важна высокая производительность.</span><span class="sxs-lookup"><span data-stu-id="8a52d-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="8a52d-172">Это позволяет избежать создания массива объектов при вызове API с небольшим числом аргументов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="8a52d-173">Имена параметров образуют единственном параметра массива и добавление числовой суффикс.</span><span class="sxs-lookup"><span data-stu-id="8a52d-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="8a52d-174">Это следует только сделать Если предполагается особым путь весь код, не просто создать массив и вызвать метод более общими.</span><span class="sxs-lookup"><span data-stu-id="8a52d-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="8a52d-175">**✓ DO** Имейте в виду, null может быть передан в качестве аргумента массива params.</span><span class="sxs-lookup"><span data-stu-id="8a52d-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="8a52d-176">Обязательно проверяйте, что массив не равен null, если перед обработкой.</span><span class="sxs-lookup"><span data-stu-id="8a52d-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="8a52d-177">**X DO NOT** использовать `varargs` методы, также известный как кнопку с многоточием.</span><span class="sxs-lookup"><span data-stu-id="8a52d-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="8a52d-178">Некоторых языков среды CLR, например C++, поддерживают альтернативные соглашение о передаче вызывается списки параметров переменных `varargs` методы.</span><span class="sxs-lookup"><span data-stu-id="8a52d-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="8a52d-179">Соглашение не следует на платформах, так как он не является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="8a52d-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="8a52d-180">Параметры-указатели</span><span class="sxs-lookup"><span data-stu-id="8a52d-180">Pointer Parameters</span></span>  
 <span data-ttu-id="8a52d-181">В общем случае указатели не должны отображаться в общую контактную зону структуры хорошо спроектированной управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8a52d-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="8a52d-182">В большинстве случаев, должна быть включена указатели.</span><span class="sxs-lookup"><span data-stu-id="8a52d-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="8a52d-183">Однако в некоторых случаях указатели являются обязательными в целях взаимодействия, и с использованием указателей в таких случаях подходит.</span><span class="sxs-lookup"><span data-stu-id="8a52d-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="8a52d-184">**✓ DO** предоставляют альтернативный для любого элемента, который принимает указатель в качестве аргумента, так как указатели не являются CLS-совместимыми.</span><span class="sxs-lookup"><span data-stu-id="8a52d-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="8a52d-185">**X AVOID** затратного контроля аргументов указатель аргументов.</span><span class="sxs-lookup"><span data-stu-id="8a52d-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="8a52d-186">**✓ DO** соглашениям общих указателей при разработке члены с указателями.</span><span class="sxs-lookup"><span data-stu-id="8a52d-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="8a52d-187">Например нет необходимости передавать начальный индекс, так как простой указателями может использоваться для достижения такого же результата.</span><span class="sxs-lookup"><span data-stu-id="8a52d-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="8a52d-188">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="8a52d-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8a52d-189">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="8a52d-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a52d-190">См. также</span><span class="sxs-lookup"><span data-stu-id="8a52d-190">See also</span></span>

- [<span data-ttu-id="8a52d-191">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="8a52d-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="8a52d-192">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="8a52d-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
