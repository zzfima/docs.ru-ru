---
title: COM-взаимодействие
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
ms.openlocfilehash: dcfdb5f3661292dda2e084eca22afab9bbec15d3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348007"
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="8c5a3-102">COM-взаимодействие (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c5a3-102">COM Interop (Visual Basic)</span></span>
<span data-ttu-id="8c5a3-103">Объектная модель компонентов (модель COM) позволяет объекту предоставлять свою функциональность другим компонентам и ведущим приложениям.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="8c5a3-104">COM-объекты входят в состав большей части современного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="8c5a3-105">Хотя сборки .NET являются наилучшим решением для новых приложений, в некоторых случаях необходимо использование COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="8c5a3-106">В этом разделе рассматриваются некоторые проблемы, связанные с созданием и использованием COM-объектов с Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-106">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c5a3-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8c5a3-107">In This Section</span></span>  
 [<span data-ttu-id="8c5a3-108">Знакомство с COM-взаимодействием</span><span class="sxs-lookup"><span data-stu-id="8c5a3-108">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 <span data-ttu-id="8c5a3-109">Общие сведения о COM-взаимодействии.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="8c5a3-110">Практическое руководство. Ссылки на COM-объекты в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c5a3-110">How to: Reference COM Objects from Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-reference-com-objects.md)  
 <span data-ttu-id="8c5a3-111">Описывает, как добавлять ссылки на COM-объекты, имеющие библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="8c5a3-112">Практическое руководство. Работа с элементами управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="8c5a3-112">How to: Work with ActiveX Controls</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 <span data-ttu-id="8c5a3-113">Демонстрирует использование существующих элементов управления ActiveX для добавления компонентов в панель элементов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-113">Demonstrates how to use existing ActiveX controls to add features to the Visual Studio Toolbox.</span></span>  
  
 [<span data-ttu-id="8c5a3-114">Пошаговое руководство. Вызов API-интерфейсов Windows</span><span class="sxs-lookup"><span data-stu-id="8c5a3-114">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="8c5a3-115">Пошаговое описание процесса вызова API-интерфейсов, входящих в операционную систему Windows.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="8c5a3-116">Практическое руководство. Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="8c5a3-116">How to: Call Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 <span data-ttu-id="8c5a3-117">Демонстрация определения и вызова функции `MessageBox` в библиотеке User32.dll.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="8c5a3-118">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="8c5a3-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="8c5a3-119">Демонстрация вызова функции Windows, которая имеет параметр с типом без знака.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="8c5a3-120">Пошаговое руководство. Создание объектов COM с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c5a3-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 <span data-ttu-id="8c5a3-121">Пошаговое описание создания COM-объектов с использованием шаблона класса COM и без него.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="8c5a3-122">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8c5a3-122">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 <span data-ttu-id="8c5a3-123">Описание некоторых проблем, которые могут возникнуть при использовании модели COM.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="8c5a3-124">COM-взаимодействие в приложениях .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8c5a3-124">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="8c5a3-125">Общие сведения об использовании объектов .NET Framework и COM в одном приложении.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="8c5a3-126">Пошаговое руководство. Реализация наследования с использованием COM-объектов</span><span class="sxs-lookup"><span data-stu-id="8c5a3-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="8c5a3-127">Описание использования существующих COM-объектов в качестве основы для новых объектов.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c5a3-128">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8c5a3-128">Related Sections</span></span>  
 [<span data-ttu-id="8c5a3-129">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="8c5a3-129">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="8c5a3-130">Описываются службы взаимодействия, предоставляемые средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="8c5a3-131">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8c5a3-131">Exposing COM Components to the .NET Framework</span></span>](../../../framework/interop/exposing-com-components.md)  
 <span data-ttu-id="8c5a3-132">Описание процесса вызова типов COM через COM-взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="8c5a3-133">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="8c5a3-133">Exposing .NET Framework Components to COM</span></span>](../../../framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="8c5a3-134">Описание подготовки и использования управляемых типов из COM.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="8c5a3-135">Применение атрибутов взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8c5a3-135">Applying Interop Attributes</span></span>](../../../standard/native-interop/apply-interop-attributes.md)  
 <span data-ttu-id="8c5a3-136">Описание атрибутов, которые можно использовать при работе с неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="8c5a3-136">Covers attributes you can use when working with unmanaged code.</span></span>
