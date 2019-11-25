---
title: Attributes overview
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: 97a2a13102718b6ee8829fca678b2b49df21e5d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349484"
---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="9dda4-102">Общие сведения об атрибутах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dda4-102">Attributes overview (Visual Basic)</span></span>

<span data-ttu-id="9dda4-103">Атрибуты предоставляют мощное средство для связывания метаданных или декларативной информации с кодом (сборки, типы, методы, свойства и т. д.).</span><span class="sxs-lookup"><span data-stu-id="9dda4-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="9dda4-104">Связав атрибут связан с сущностью программы, вы можете проверять этот атрибут во время выполнения, используя технику *отражения*.</span><span class="sxs-lookup"><span data-stu-id="9dda4-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="9dda4-105">Дополнительные сведения см. в статье [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="9dda4-105">For more information, see [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span></span>

<span data-ttu-id="9dda4-106">Атрибуты имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9dda4-106">Attributes have the following properties:</span></span>

- <span data-ttu-id="9dda4-107">Атрибуты добавляют в программу метаданные.</span><span class="sxs-lookup"><span data-stu-id="9dda4-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="9dda4-108">*Метаданные* — это сведения о типах, определенных в программе.</span><span class="sxs-lookup"><span data-stu-id="9dda4-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="9dda4-109">Все сборки .NET содержат некоторый набор метаданных, описывающих типы и члены типов, определенные в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="9dda4-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="9dda4-110">Вы можете добавить пользовательские атрибуты, чтобы указать любую дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="9dda4-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="9dda4-111">Дополнительные сведения см. в статье [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание пользовательских атрибутов (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="9dda4-111">For more information, see, [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>

- <span data-ttu-id="9dda4-112">Вы можете применить один или несколько атрибутов ко всей сборке, к модулю или к более мелким элементам программы, например к классам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="9dda4-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>

- <span data-ttu-id="9dda4-113">Атрибуты могут принимать аргументы, так же как методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="9dda4-113">Attributes can accept arguments in the same way as methods and properties.</span></span>

- <span data-ttu-id="9dda4-114">Программа может проверить собственные метаданные или метаданные в других программах, используя отражение.</span><span class="sxs-lookup"><span data-stu-id="9dda4-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="9dda4-115">Дополнительные сведения см. в статье [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="9dda4-115">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>

## <a name="using-attributes"></a><span data-ttu-id="9dda4-116">Использование атрибутов</span><span class="sxs-lookup"><span data-stu-id="9dda4-116">Using Attributes</span></span>

<span data-ttu-id="9dda4-117">Атрибуты можно использовать почти в любых объявлениях, но для каждого атрибута можно ограничить типы объявлений, в которых он является допустимым.</span><span class="sxs-lookup"><span data-stu-id="9dda4-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="9dda4-118">В Visual Basic атрибуты заключаются в угловые скобки (\< >).</span><span class="sxs-lookup"><span data-stu-id="9dda4-118">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="9dda4-119">Они должны располагаться непосредственно перед тем элементом, к которому они применяются, и обязательно в той же строке.</span><span class="sxs-lookup"><span data-stu-id="9dda4-119">It must appear immediately before the element to which it is applied, on the same line.</span></span>

<span data-ttu-id="9dda4-120">В этом примере атрибут <xref:System.SerializableAttribute> используется для применения определенной характеристики к классу:</span><span class="sxs-lookup"><span data-stu-id="9dda4-120">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 <span data-ttu-id="9dda4-121">Метод с атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute> объявляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9dda4-121">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

<span data-ttu-id="9dda4-122">В объявлении можно разместить несколько атрибутов:</span><span class="sxs-lookup"><span data-stu-id="9dda4-122">More than one attribute can be placed on a declaration:</span></span>

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

<span data-ttu-id="9dda4-123">Некоторые атрибуты можно указать для одной сущности более одного раза.</span><span class="sxs-lookup"><span data-stu-id="9dda4-123">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="9dda4-124">Пример такого многократно используемого атрибута — <xref:System.Diagnostics.ConditionalAttribute>:</span><span class="sxs-lookup"><span data-stu-id="9dda4-124">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> <span data-ttu-id="9dda4-125">По соглашению все имена атрибутов заканчиваются словом "Attribute", чтобы отличать их от других элементов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dda4-125">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="9dda4-126">Но при использовании атрибута в коде этот суффикс можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="9dda4-126">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="9dda4-127">Например, обращение `[DllImport]` эквивалентно `[DllImportAttribute]`, хотя в .NET Framework этот атрибут имеет имя `DllImportAttribute`.</span><span class="sxs-lookup"><span data-stu-id="9dda4-127">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>

### <a name="attribute-parameters"></a><span data-ttu-id="9dda4-128">Параметры атрибутов</span><span class="sxs-lookup"><span data-stu-id="9dda4-128">Attribute Parameters</span></span>

<span data-ttu-id="9dda4-129">Многие атрибуты имеют параметры, которые могут быть позиционными, неименованными или именованными.</span><span class="sxs-lookup"><span data-stu-id="9dda4-129">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="9dda4-130">Позиционные параметры необходимо указывать в строгом порядке и их нельзя опускать. Именованные параметры являются необязательными и их можно указывать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="9dda4-130">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="9dda4-131">Сначала указываются позиционные параметры.</span><span class="sxs-lookup"><span data-stu-id="9dda4-131">Positional parameters are specified first.</span></span> <span data-ttu-id="9dda4-132">Например, эти три атрибута являются эквивалентными:</span><span class="sxs-lookup"><span data-stu-id="9dda4-132">For example, these three attributes are equivalent:</span></span>

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

<span data-ttu-id="9dda4-133">Первый параметр (имя библиотеки DLL) является позиционным и всегда располагается первым, остальные параметры являются именованными.</span><span class="sxs-lookup"><span data-stu-id="9dda4-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="9dda4-134">В этом примере оба именованных параметра имеют значение по умолчанию (false), и мы можем их опустить.</span><span class="sxs-lookup"><span data-stu-id="9dda4-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="9dda4-135">Сведения о значениях параметров по умолчанию указываются в документации по каждому отдельному атрибуту.</span><span class="sxs-lookup"><span data-stu-id="9dda4-135">Refer to the individual attribute's documentation for information on default parameter values.</span></span>

### <a name="attribute-targets"></a><span data-ttu-id="9dda4-136">Целевые объекты атрибутов</span><span class="sxs-lookup"><span data-stu-id="9dda4-136">Attribute Targets</span></span>

<span data-ttu-id="9dda4-137">*Целевой объект* атрибута — это сущность, к которой применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="9dda4-137">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="9dda4-138">Например, атрибут можно применить к классу, отдельному методу или ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="9dda4-138">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="9dda4-139">По умолчанию атрибут применяется к тому элементу, перед которым он указан.</span><span class="sxs-lookup"><span data-stu-id="9dda4-139">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="9dda4-140">Но у вас есть возможность явным образом указать, например, что атрибут применяется к методу, параметру или возвращаемому значению.</span><span class="sxs-lookup"><span data-stu-id="9dda4-140">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>

<span data-ttu-id="9dda4-141">Чтобы явным образом определить целевой объект атрибута, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9dda4-141">To explicitly identify an attribute target, use the following syntax:</span></span>

```vb
<target : attribute-list>
```

<span data-ttu-id="9dda4-142">Возможные значения `target` перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9dda4-142">The list of possible `target` values is shown in the following table.</span></span>

|<span data-ttu-id="9dda4-143">Целевое значение</span><span class="sxs-lookup"><span data-stu-id="9dda4-143">Target value</span></span>|<span data-ttu-id="9dda4-144">Применение</span><span class="sxs-lookup"><span data-stu-id="9dda4-144">Applies to</span></span>|
|------------------|----------------|
|`assembly`|<span data-ttu-id="9dda4-145">Вся сборка</span><span class="sxs-lookup"><span data-stu-id="9dda4-145">Entire assembly</span></span>|
|`module`|<span data-ttu-id="9dda4-146">Текущий модуль сборки (это не то же самое, что модуль Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dda4-146">Current assembly module (which is different from a Visual Basic Module)</span></span>|

 <span data-ttu-id="9dda4-147">Следующий пример демонстрирует, как применить атрибуты к сборкам и модулям.</span><span class="sxs-lookup"><span data-stu-id="9dda4-147">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="9dda4-148">Дополнительные сведения см. в статье [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Распространенные атрибуты (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="9dda4-148">For more information, see [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md).</span></span>

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

## <a name="common-uses-for-attributes"></a><span data-ttu-id="9dda4-149">Популярные методы применения атрибутов</span><span class="sxs-lookup"><span data-stu-id="9dda4-149">Common Uses for Attributes</span></span>

<span data-ttu-id="9dda4-150">В следующем списке перечислены несколько распространенных применений для атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9dda4-150">The following list includes a few of the common uses of attributes in code:</span></span>

- <span data-ttu-id="9dda4-151">Указание для методов в веб-службах атрибута `WebMethod`, который обозначает, что метод должен вызываться по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="9dda4-151">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="9dda4-152">Для получения дополнительной информации см. <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9dda4-152">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>

- <span data-ttu-id="9dda4-153">Описание способов упаковки параметров методов при взаимодействии с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="9dda4-153">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="9dda4-154">Для получения дополнительной информации см. <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9dda4-154">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

- <span data-ttu-id="9dda4-155">Описание свойств COM для классов, методов и интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="9dda4-155">Describing the COM properties for classes, methods, and interfaces.</span></span>

- <span data-ttu-id="9dda4-156">Вызов неуправляемого кода с помощью класса <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9dda4-156">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>

- <span data-ttu-id="9dda4-157">Указание для сборки таких параметров, как заголовок, версия, описание или товарный знак.</span><span class="sxs-lookup"><span data-stu-id="9dda4-157">Describing your assembly in terms of title, version, description, or trademark.</span></span>

- <span data-ttu-id="9dda4-158">Указание членов класса, которые будут сериализованы при сохранении класса.</span><span class="sxs-lookup"><span data-stu-id="9dda4-158">Describing which members of a class to serialize for persistence.</span></span>

- <span data-ttu-id="9dda4-159">Описание правил сопоставления членов класса с XML-узлами при XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="9dda4-159">Describing how to map between class members and XML nodes for XML serialization.</span></span>

- <span data-ttu-id="9dda4-160">Описание требований безопасности для методов.</span><span class="sxs-lookup"><span data-stu-id="9dda4-160">Describing the security requirements for methods.</span></span>

- <span data-ttu-id="9dda4-161">Указание характеристик, используемых для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="9dda4-161">Specifying characteristics used to enforce security.</span></span>

- <span data-ttu-id="9dda4-162">Управление оптимизацией для JIT-компилятора, сохраняя при этом простоту отладки кода.</span><span class="sxs-lookup"><span data-stu-id="9dda4-162">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>

- <span data-ttu-id="9dda4-163">Получение сведений об объекте, вызывающем метод.</span><span class="sxs-lookup"><span data-stu-id="9dda4-163">Obtaining information about the caller to a method.</span></span>

## <a name="related-sections"></a><span data-ttu-id="9dda4-164">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9dda4-164">Related Sections</span></span>

<span data-ttu-id="9dda4-165">Дополнительные сведения см. на странице</span><span class="sxs-lookup"><span data-stu-id="9dda4-165">For more information, see:</span></span>

- <span data-ttu-id="9dda4-166">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание настраиваемых атрибутов (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9dda4-166">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>

- <span data-ttu-id="9dda4-167">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9dda4-167">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>

- <span data-ttu-id="9dda4-168">[How to: Create a C/C++ Union by Using Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md) (Практическое руководство. Создание объединения C/C++ с помощью атрибутов (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9dda4-168">[How to: Create a C/C++ Union by Using Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)</span></span>

- <span data-ttu-id="9dda4-169">[Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) (Распространенные атрибуты (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9dda4-169">[Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)</span></span>

- <span data-ttu-id="9dda4-170">[Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md) (Сведения о вызывающем (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9dda4-170">[Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="9dda4-171">См. также</span><span class="sxs-lookup"><span data-stu-id="9dda4-171">See also</span></span>

- [<span data-ttu-id="9dda4-172">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9dda4-172">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- <span data-ttu-id="9dda4-173">[Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9dda4-173">[Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)</span></span>
- [<span data-ttu-id="9dda4-174">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9dda4-174">Attributes</span></span>](../../../../standard/attributes/index.md)
