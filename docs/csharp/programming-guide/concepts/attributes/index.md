---
title: "Атрибуты (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ab55021a073f914905e29163ba2a669f69d6dcab
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="attributes-c"></a><span data-ttu-id="77393-102">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="77393-102">Attributes (C#)</span></span>
<span data-ttu-id="77393-103">Атрибуты предоставляют мощное средство для связывания метаданных или декларативной информации с кодом (сборки, типы, методы, свойства и т. д.).</span><span class="sxs-lookup"><span data-stu-id="77393-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="77393-104">Связав атрибут связан с сущностью программы, вы можете проверять этот атрибут во время выполнения, используя технику *отражения*.</span><span class="sxs-lookup"><span data-stu-id="77393-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="77393-105">Подробнее см. в разделе [Отражение (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="77393-105">For more information, see [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="77393-106">Атрибуты имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="77393-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="77393-107">Атрибуты добавляют в программу метаданные.</span><span class="sxs-lookup"><span data-stu-id="77393-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="77393-108">*Метаданные* — это сведения о типах, определенных в программе.</span><span class="sxs-lookup"><span data-stu-id="77393-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="77393-109">Все сборки .NET содержат некоторый набор метаданных, описывающих типы и члены типов, определенные в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="77393-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="77393-110">Вы можете добавить пользовательские атрибуты, чтобы указать любую дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="77393-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="77393-111">Подробнее см. в разделе [Создание настраиваемых атрибутов (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="77393-111">For more information, see, [Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="77393-112">Вы можете применить один или несколько атрибутов ко всей сборке, к модулю или к более мелким элементам программы, например к классам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="77393-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="77393-113">Атрибуты могут принимать аргументы, так же как методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="77393-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="77393-114">Программа может проверить собственные метаданные или метаданные в других программах, используя отражение.</span><span class="sxs-lookup"><span data-stu-id="77393-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="77393-115">Дополнительные сведения см. в разделе [Обращение к атрибутам с помощью отражения (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="77393-115">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="77393-116">Использование атрибутов</span><span class="sxs-lookup"><span data-stu-id="77393-116">Using Attributes</span></span>  
 <span data-ttu-id="77393-117">Атрибуты можно использовать почти в любых объявлениях, но для каждого атрибута можно ограничить типы объявлений, в которых он является допустимым.</span><span class="sxs-lookup"><span data-stu-id="77393-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="77393-118">Чтобы указать атрибут на C#, поместите имя атрибута в квадратных скобках ([]) над объявлением сущности, к которой он применяется.</span><span class="sxs-lookup"><span data-stu-id="77393-118">In C#, you specify an attribute by placing the name of the attribute, enclosed in square brackets ([]), above the declaration of the entity to which it applies.</span></span>  
  
 <span data-ttu-id="77393-119">В этом примере атрибут <xref:System.SerializableAttribute> используется для применения определенной характеристики к классу:</span><span class="sxs-lookup"><span data-stu-id="77393-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 <span data-ttu-id="77393-120">Метод с атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute> объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="77393-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 <span data-ttu-id="77393-121">В объявлении можно разместить несколько атрибутов:</span><span class="sxs-lookup"><span data-stu-id="77393-121">More than one attribute can be placed on a declaration:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 <span data-ttu-id="77393-122">Некоторые атрибуты можно указать для одной сущности более одного раза.</span><span class="sxs-lookup"><span data-stu-id="77393-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="77393-123">Пример такого многократно используемого атрибута — <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="77393-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="77393-124">По соглашению все имена атрибутов заканчиваются словом "Attribute", чтобы отличать их от других элементов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77393-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="77393-125">Но при использовании атрибута в коде этот суффикс можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="77393-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="77393-126">Например, обращение `[DllImport]` эквивалентно `[DllImportAttribute]`, хотя в .NET Framework этот атрибут имеет имя `DllImportAttribute`.</span><span class="sxs-lookup"><span data-stu-id="77393-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="77393-127">Параметры атрибутов</span><span class="sxs-lookup"><span data-stu-id="77393-127">Attribute Parameters</span></span>  
 <span data-ttu-id="77393-128">Многие атрибуты имеют параметры, которые могут быть позиционными, неименованными или именованными.</span><span class="sxs-lookup"><span data-stu-id="77393-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="77393-129">Позиционные параметры необходимо указывать в строгом порядке и их нельзя опускать. Именованные параметры являются необязательными и их можно указывать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="77393-129">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="77393-130">Сначала указываются позиционные параметры.</span><span class="sxs-lookup"><span data-stu-id="77393-130">Positional parameters are specified first.</span></span> <span data-ttu-id="77393-131">Например, эти три атрибута являются эквивалентными:</span><span class="sxs-lookup"><span data-stu-id="77393-131">For example, these three attributes are equivalent:</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 <span data-ttu-id="77393-132">Первый параметр (имя библиотеки DLL) является позиционным и всегда располагается первым, остальные параметры являются именованными.</span><span class="sxs-lookup"><span data-stu-id="77393-132">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="77393-133">В этом примере оба именованных параметра имеют значение по умолчанию (false), и мы можем их опустить.</span><span class="sxs-lookup"><span data-stu-id="77393-133">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="77393-134">Сведения о значениях параметров по умолчанию указываются в документации по каждому отдельному атрибуту.</span><span class="sxs-lookup"><span data-stu-id="77393-134">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="77393-135">Целевые объекты атрибутов</span><span class="sxs-lookup"><span data-stu-id="77393-135">Attribute Targets</span></span>  
 <span data-ttu-id="77393-136">*Целевой объект* атрибута — это сущность, к которой применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="77393-136">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="77393-137">Например, атрибут можно применить к классу, отдельному методу или ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="77393-137">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="77393-138">По умолчанию атрибут применяется к тому элементу, перед которым он указан.</span><span class="sxs-lookup"><span data-stu-id="77393-138">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="77393-139">Но у вас есть возможность явным образом указать, например, что атрибут применяется к методу, параметру или возвращаемому значению.</span><span class="sxs-lookup"><span data-stu-id="77393-139">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="77393-140">Чтобы явным образом определить целевой объект атрибута, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="77393-140">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```csharp  
[target : attribute-list]  
```  
  
 <span data-ttu-id="77393-141">Возможные значения `target` перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="77393-141">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="77393-142">Целевое значение</span><span class="sxs-lookup"><span data-stu-id="77393-142">Target value</span></span>|<span data-ttu-id="77393-143">Применение</span><span class="sxs-lookup"><span data-stu-id="77393-143">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="77393-144">Вся сборка</span><span class="sxs-lookup"><span data-stu-id="77393-144">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="77393-145">Модуль текущей сборки</span><span class="sxs-lookup"><span data-stu-id="77393-145">Current assembly module</span></span>|  
|`field`|<span data-ttu-id="77393-146">Поле в классе или структуре</span><span class="sxs-lookup"><span data-stu-id="77393-146">Field in a class or a struct</span></span>|  
|`event`|<span data-ttu-id="77393-147">Событие</span><span class="sxs-lookup"><span data-stu-id="77393-147">Event</span></span>|  
|`method`|<span data-ttu-id="77393-148">Метод либо методы доступа к свойствам `get` и `set`</span><span class="sxs-lookup"><span data-stu-id="77393-148">Method or `get` and `set` property accessors</span></span>|  
|`param`|<span data-ttu-id="77393-149">Параметры метода или параметры метода доступа `set`</span><span class="sxs-lookup"><span data-stu-id="77393-149">Method parameters or `set` property accessor parameters</span></span>|  
|`property`|<span data-ttu-id="77393-150">Свойство</span><span class="sxs-lookup"><span data-stu-id="77393-150">Property</span></span>|  
|`return`|<span data-ttu-id="77393-151">Возвращаемое значение метода, индексатора свойства или метода доступа к свойствам `get`</span><span class="sxs-lookup"><span data-stu-id="77393-151">Return value of a method, property indexer, or `get` property accessor</span></span>|  
|`type`|<span data-ttu-id="77393-152">Структура, класс, интерфейс, перечисление или делегат</span><span class="sxs-lookup"><span data-stu-id="77393-152">Struct, class, interface, enum, or delegate</span></span>|  
  
 <span data-ttu-id="77393-153">Следующий пример демонстрирует, как применить атрибуты к сборкам и модулям.</span><span class="sxs-lookup"><span data-stu-id="77393-153">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="77393-154">Дополнительные сведения см. в разделе [Общие атрибуты (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="77393-154">For more information, see [Common Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 <span data-ttu-id="77393-155">В следующем примере показано, как применять атрибуты к методам, параметрам и возвращаемым значениям методов в C#.</span><span class="sxs-lookup"><span data-stu-id="77393-155">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  <span data-ttu-id="77393-156">Вне зависимости от целевых объектов, для которых действует атрибут `SomeAttr`, необходимо задать целевой объект для `return`, даже если атрибут `SomeAttr` назначен только возвращаемым значениям.</span><span class="sxs-lookup"><span data-stu-id="77393-156">Regardless of the targets on which `SomeAttr` is defined to be valid, the `return` target has to be specified, even if `SomeAttr` were defined to apply only to return values.</span></span> <span data-ttu-id="77393-157">Другими словами, компилятор не будет использовать сведения `AttributeUsage` для разрешения конфликтов между неоднозначными целевыми объектами атрибута.</span><span class="sxs-lookup"><span data-stu-id="77393-157">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="77393-158">Подробнее см. в разделе [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span><span class="sxs-lookup"><span data-stu-id="77393-158">For more information, see [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span></span>  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="77393-159">Популярные методы применения атрибутов</span><span class="sxs-lookup"><span data-stu-id="77393-159">Common Uses for Attributes</span></span>  
 <span data-ttu-id="77393-160">В следующем списке перечислены несколько распространенных применений для атрибутов.</span><span class="sxs-lookup"><span data-stu-id="77393-160">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="77393-161">Указание для методов в веб-службах атрибута `WebMethod`, который обозначает, что метод должен вызываться по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="77393-161">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="77393-162">Для получения дополнительной информации см. <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77393-162">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="77393-163">Описание способов упаковки параметров методов при взаимодействии с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="77393-163">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="77393-164">Для получения дополнительной информации см. <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77393-164">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="77393-165">Описание свойств COM для классов, методов и интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="77393-165">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="77393-166">Вызов неуправляемого кода с помощью класса <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77393-166">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="77393-167">Указание для сборки таких параметров, как заголовок, версия, описание или товарный знак.</span><span class="sxs-lookup"><span data-stu-id="77393-167">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="77393-168">Указание членов класса, которые будут сериализованы при сохранении класса.</span><span class="sxs-lookup"><span data-stu-id="77393-168">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="77393-169">Описание правил сопоставления членов класса с XML-узлами при XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="77393-169">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="77393-170">Описание требований безопасности для методов.</span><span class="sxs-lookup"><span data-stu-id="77393-170">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="77393-171">Указание характеристик, используемых для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="77393-171">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="77393-172">Управление оптимизацией для JIT-компилятора, сохраняя при этом простоту отладки кода.</span><span class="sxs-lookup"><span data-stu-id="77393-172">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="77393-173">Получение сведений об объекте, вызывающем метод.</span><span class="sxs-lookup"><span data-stu-id="77393-173">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77393-174">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="77393-174">Related Sections</span></span>  
 <span data-ttu-id="77393-175">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="77393-175">For more information, see:</span></span>  
  
-   [<span data-ttu-id="77393-176">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="77393-176">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [<span data-ttu-id="77393-177">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="77393-177">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [<span data-ttu-id="77393-178">Практическое руководство. Создание объединения C/C++ с помощью атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="77393-178">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="77393-179">Общие атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="77393-179">Common Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   <span data-ttu-id="77393-180">[Caller Information (C#)](../../../../csharp/programming-guide/concepts/caller-information.md) (Сведения о вызывающем объекте (C#))</span><span class="sxs-lookup"><span data-stu-id="77393-180">[Caller Information (C#)](../../../../csharp/programming-guide/concepts/caller-information.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77393-181">См. также</span><span class="sxs-lookup"><span data-stu-id="77393-181">See Also</span></span>  
 <span data-ttu-id="77393-182">[Руководство по программированию на C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="77393-182">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="77393-183">[Отражение (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="77393-183">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 [<span data-ttu-id="77393-184">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="77393-184">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

