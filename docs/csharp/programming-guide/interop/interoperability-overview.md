---
title: "Общие сведения о взаимодействии. (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c817dcd9073a5a1d4aeee558bf53d50566bbb472
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="interoperability-overview-c-programming-guide"></a><span data-ttu-id="4d5d2-102">Общие сведения о взаимодействии. (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="4d5d2-102">Interoperability Overview (C# Programming Guide)</span></span>
<span data-ttu-id="4d5d2-103">В этом разделе описываются способы включения взаимодействия между управляемым кодом C# и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-103">The topic describes methods to enable interoperability between C# managed code and unmanaged code.</span></span>  
  
## <a name="platform-invoke"></a><span data-ttu-id="4d5d2-104">Вызов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="4d5d2-104">Platform Invoke</span></span>  
 <span data-ttu-id="4d5d2-105">*Вызов неуправляемого кода* — это служба, позволяющая управляемому коду вызывать неуправляемые функции, реализованные в библиотеках динамической компоновки (DLL), например функции библиотек Microsoft Win32 API.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-105">*Platform invoke* is a service that enables managed code to call unmanaged functions that are implemented in dynamic link libraries (DLLs), such as those in the Microsoft Win32 API.</span></span> <span data-ttu-id="4d5d2-106">Он обнаруживает и вызывает экспортированную функцию и при необходимости маршалирует ее аргументы (целые числа, строки, массивы, структуры и так далее) через границы взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-106">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="4d5d2-107">Дополнительные сведения см. в разделах [Использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md) и [Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span><span class="sxs-lookup"><span data-stu-id="4d5d2-107">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) and [How to: Use Platform Invoke to Play a Wave File](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d5d2-108">[Среда CLR](../../../standard/clr.md) управляет доступом к системным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-108">The [Common Language Runtime](../../../standard/clr.md) (CLR) manages access to system resources.</span></span> <span data-ttu-id="4d5d2-109">Вызов неуправляемого кода, который находится вне среды CLR, обходит этот механизм защиты и таким образом представляет угрозу безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-109">Calling unmanaged code that is outside the CLR bypasses this security mechanism, and therefore presents a security risk.</span></span> <span data-ttu-id="4d5d2-110">Например, неуправляемый код может обращаться к ресурсам в неуправляемом коде напрямую, минуя механизмы обеспечения безопасности среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-110">For example, unmanaged code might call resources in unmanaged code directly, bypassing CLR security mechanisms.</span></span> <span data-ttu-id="4d5d2-111">Дополнительные сведения см. в разделе [Безопасность .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).</span><span class="sxs-lookup"><span data-stu-id="4d5d2-111">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="c-interop"></a><span data-ttu-id="4d5d2-112">взаимодействие C++</span><span class="sxs-lookup"><span data-stu-id="4d5d2-112">C++ Interop</span></span>  
 <span data-ttu-id="4d5d2-113">Взаимодействие C++, также известное как IJW, можно использовать для создания оболочки для собственного класса C++ для использования в коде, созданном на C# или другом языке .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-113">You can use C++ interop, also known as It Just Works (IJW), to wrap a native C++ class so that it can be consumed by code that is authored in C# or another .NET Framework language.</span></span> <span data-ttu-id="4d5d2-114">Для этого необходимо написать код C++, создающий оболочку для собственного DLL- или COM-компонента.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-114">To do this, you write C++ code to wrap a native DLL or COM component.</span></span> <span data-ttu-id="4d5d2-115">В отличие от других языков .NET Framework, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] включает поддержку взаимодействия, что позволяет размещать управляемый и неуправляемый код в одном приложении и даже в одном файле.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-115">Unlike other .NET Framework languages, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] has interoperability support that enables managed and unmanaged code to be located in the same application and even in the same file.</span></span> <span data-ttu-id="4d5d2-116">Затем вы выполняете сборку кода C++ с помощью параметра компилятора **/clr** для создания управляемой сборки.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-116">You then build the C++ code by using the **/clr** compiler switch to produce a managed assembly.</span></span> <span data-ttu-id="4d5d2-117">И, наконец, необходимо добавить ссылку на сборку в проекте C# и использовать объекты с оболочкой так же, как другие управляемые классы.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-117">Finally, you add a reference to the assembly in your C# project and use the wrapped objects just as you would use other managed classes.</span></span>  
  
## <a name="exposing-com-components-to-c"></a><span data-ttu-id="4d5d2-118">Предоставление доступа к COM-компонентам кода C#</span><span class="sxs-lookup"><span data-stu-id="4d5d2-118">Exposing COM Components to C#</span></span>  
 <span data-ttu-id="4d5d2-119">Вы можете использовать COM-компоненты в проекте C#.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-119">You can consume a COM component from a C# project.</span></span> <span data-ttu-id="4d5d2-120">Общая процедура следующая.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-120">The general steps are as follows:</span></span>  
  
1.  <span data-ttu-id="4d5d2-121">Найдите нужный COM-компонент и зарегистрируйте его.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-121">Locate a COM component to use and register it.</span></span> <span data-ttu-id="4d5d2-122">Используйте regsvr32.exe для регистрации или отмены регистрации библиотеки DLL модели COM.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-122">Use regsvr32.exe to register or un–register a COM DLL.</span></span>  
  
2.  <span data-ttu-id="4d5d2-123">Добавьте в проект ссылку на COM-компонент или библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-123">Add to the project a reference to the COM component or type library.</span></span>  
  
     <span data-ttu-id="4d5d2-124">При добавлении ссылки [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] использует программу [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), принимающую библиотеки типов в качестве входных данных, для вывода сборки взаимодействия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-124">When you add the reference, [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses the [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), which takes a type library as input, to output a .NET Framework interop assembly.</span></span> <span data-ttu-id="4d5d2-125">Сборка, также называемая вызываемой оболочкой времени выполнения (RCW), содержит управляемые классы и интерфейсы, которые служат оболочкой для классов и интерфейсов COM в библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-125">The assembly, also named a runtime callable wrapper (RCW), contains managed classes and interfaces that wrap the COM classes and interfaces that are in the type library.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="4d5d2-126"> добавляет в проект ссылку на созданную сборку.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-126"> adds to the project a reference to the generated assembly.</span></span>  
  
3.  <span data-ttu-id="4d5d2-127">Создайте экземпляр класса, определенного в вызываемой оболочке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-127">Create an instance of a class that is defined in the RCW.</span></span> <span data-ttu-id="4d5d2-128">Он, в свою очередь, создает экземпляр COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-128">This, in turn, creates an instance of the COM object.</span></span>  
  
4.  <span data-ttu-id="4d5d2-129">Используйте объект так же, как другие управляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-129">Use the object just as you use other managed objects.</span></span> <span data-ttu-id="4d5d2-130">Когда объект удаляется сборщиком мусора, экземпляр COM-объекта также удаляется из памяти.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-130">When the object is reclaimed by garbage collection, the instance of the COM object is also released from memory.</span></span>  
  
 <span data-ttu-id="4d5d2-131">Дополнительные сведения см. в статье [Предоставление клиентам .NET Framework доступа к COM-компонентам](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span><span class="sxs-lookup"><span data-stu-id="4d5d2-131">For more information, see [Exposing COM Components to the .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).</span></span>  
  
## <a name="exposing-c-to-com"></a><span data-ttu-id="4d5d2-132">Предоставление C# клиентам COM</span><span class="sxs-lookup"><span data-stu-id="4d5d2-132">Exposing C# to COM</span></span>  
 <span data-ttu-id="4d5d2-133">Клиенты COM могут потреблять типы C#, которые были правильно предоставлены.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-133">COM clients can consume C# types that have been correctly exposed.</span></span> <span data-ttu-id="4d5d2-134">Ниже приведены основные шаги для предоставления типов C#.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-134">The basic steps to expose C# types are as follows:</span></span>  
  
1.  <span data-ttu-id="4d5d2-135">Добавьте атрибуты взаимодействия в проект C#.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-135">Add interop attributes in the C# project.</span></span>  
  
     <span data-ttu-id="4d5d2-136">Сборку COM можно сделать видимой, изменив свойства проекта [!INCLUDE[csprcs](~/includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d5d2-136">You can make an assembly COM visible by modifying [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties.</span></span> <span data-ttu-id="4d5d2-137">Дополнительные сведения см. в разделе [Диалоговое окно "Сведения о сборке"](/visualstudio/ide/reference/assembly-information-dialog-box).</span><span class="sxs-lookup"><span data-stu-id="4d5d2-137">For more information, see [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box).</span></span>  
  
2.  <span data-ttu-id="4d5d2-138">Создайте библиотеку типов COM и зарегистрируйте ее для использования моделью COM.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-138">Generate a COM type library and register it for COM usage.</span></span>  
  
     <span data-ttu-id="4d5d2-139">Можно изменить свойства проекта [!INCLUDE[csprcs](~/includes/csprcs-md.md)] для автоматической регистрации сборки C# для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-139">You can modify [!INCLUDE[csprcs](~/includes/csprcs-md.md)] project properties to automatically register the C# assembly for COM interop.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="4d5d2-140"> использует программу [Regasm.exe (средство регистрации сборок)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb) с помощью параметра командной строки `/tlb`, которая принимает управляемую сборку в качестве входного значения, чтобы создать библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-140"> uses the [Regasm.exe (Assembly Registration Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb), using the `/tlb` command-line switch, which takes a managed assembly as input, to generate a type library.</span></span> <span data-ttu-id="4d5d2-141">Эта библиотека типов описывает типы `public` в сборке и добавляет записи реестра, чтобы клиенты COM могли создавать управляемые классы.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-141">This type library describes the `public` types in the assembly and adds registry entries so that COM clients can create managed classes.</span></span>  
  
 <span data-ttu-id="4d5d2-142">Дополнительные сведения см. в разделе [Предоставление COM-клиентам доступа к компонентам .NET Framework](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) и [Пример COM-класса](../../../csharp/programming-guide/interop/example-com-class.md).</span><span class="sxs-lookup"><span data-stu-id="4d5d2-142">For more information, see [Exposing .NET Framework Components to COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) and [Example COM Class](../../../csharp/programming-guide/interop/example-com-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5d2-143">См. также</span><span class="sxs-lookup"><span data-stu-id="4d5d2-143">See Also</span></span>  
 <span data-ttu-id="4d5d2-144">[Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564) </span><span class="sxs-lookup"><span data-stu-id="4d5d2-144">[Improving Interop Performance](http://go.microsoft.com/fwlink/?LinkId=99564) </span></span>  
 <span data-ttu-id="4d5d2-145">[Знакомство с COM-взаимодействием](http://go.microsoft.com/fwlink/?LinkId=112406) </span><span class="sxs-lookup"><span data-stu-id="4d5d2-145">[Introduction to COM Interop](http://go.microsoft.com/fwlink/?LinkId=112406) </span></span>  
 <span data-ttu-id="4d5d2-146">[Маршалинг данных между управляемым и неуправляемым кодом](http://go.microsoft.com/fwlink/?LinkId=112398) </span><span class="sxs-lookup"><span data-stu-id="4d5d2-146">[Marshaling between Managed and Unmanaged Code](http://go.microsoft.com/fwlink/?LinkId=112398) </span></span>  
 <span data-ttu-id="4d5d2-147">[Взаимодействие с неуправляемым кодом](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="4d5d2-147">[Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
 <span data-ttu-id="4d5d2-148">[Расширенное COM-взаимодействие](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span><span class="sxs-lookup"><span data-stu-id="4d5d2-148">[Advanced COM Interoperability](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span></span>  
 [<span data-ttu-id="4d5d2-149">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4d5d2-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

