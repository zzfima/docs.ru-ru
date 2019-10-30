---
title: Взаимодействие с неуправляемым кодом
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: cdd8d2781331956289d2b74162e653ba1ee8fad6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114231"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="ff40c-102">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="ff40c-102">Interoperating with unmanaged code</span></span>

<span data-ttu-id="ff40c-103">Платформа .NET Framework обеспечивает взаимодействие с COM-компонентами, службами COM+, внешними библиотеками типов и многими службами операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ff40c-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="ff40c-104">Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов.</span><span class="sxs-lookup"><span data-stu-id="ff40c-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="ff40c-105">Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="ff40c-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="ff40c-106">Код, выполняющийся под управлением среды выполнения, называется управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="ff40c-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="ff40c-107">И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="ff40c-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="ff40c-108">Примерами неуправляемого кода являются компоненты COM, интерфейсы ActiveX и функции Windows API.</span><span class="sxs-lookup"><span data-stu-id="ff40c-108">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff40c-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="ff40c-109">In this section</span></span>

[<span data-ttu-id="ff40c-110">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ff40c-110">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="ff40c-111">Описывает способы использования COM-компонентов в приложениях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff40c-111">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="ff40c-112">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="ff40c-112">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="ff40c-113">Описывает способы использования компонентов .NET Framework в приложениях COM.</span><span class="sxs-lookup"><span data-stu-id="ff40c-113">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="ff40c-114">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="ff40c-114">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="ff40c-115">Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="ff40c-115">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="ff40c-116">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ff40c-116">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="ff40c-117">Описывается маршалинг для COM-взаимодействия и вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="ff40c-117">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="ff40c-118">Практическое руководство. Сопоставление значений HRESULT и исключений</span><span class="sxs-lookup"><span data-stu-id="ff40c-118">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="ff40c-119">Описывает сопоставление исключений и значений HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ff40c-119">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="ff40c-120">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="ff40c-120">COM Wrappers</span></span>](com-wrappers.md)  
<span data-ttu-id="ff40c-121">Описываются программы-оболочки, предоставляемые COM-взаимодействием.</span><span class="sxs-lookup"><span data-stu-id="ff40c-121">Describes the wrappers provided by COM interop.</span></span>

[<span data-ttu-id="ff40c-122">Эквивалентность типов и внедренные типы взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ff40c-122">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="ff40c-123">Описывается способ внедрения сведений о типах COM в сборках и определения общеязыковой средой выполнения эквивалентности встроенных типов COM.</span><span class="sxs-lookup"><span data-stu-id="ff40c-123">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="ff40c-124">Практическое руководство. Создание основной сборки взаимодействия с помощью программы Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="ff40c-124">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="ff40c-125">Описывается способ создания основных сборок взаимодействия с помощью *Tlbimp.exe* (программа импорта библиотек типов).</span><span class="sxs-lookup"><span data-stu-id="ff40c-125">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="ff40c-126">Практическое руководство. Регистрация основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ff40c-126">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="ff40c-127">Описывается регистрация основных сборок взаимодействия до того, как на них можно будет создавать ссылки в проектах.</span><span class="sxs-lookup"><span data-stu-id="ff40c-127">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="ff40c-128">COM-взаимодействие без регистрации</span><span class="sxs-lookup"><span data-stu-id="ff40c-128">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="ff40c-129">Описывается способ активации COM-взаимодействием компонентов без использования реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="ff40c-129">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="ff40c-130">Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации</span><span class="sxs-lookup"><span data-stu-id="ff40c-130">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="ff40c-131">Описывается способ создания манифеста приложения, а также создания и внедрения манифеста компонента.</span><span class="sxs-lookup"><span data-stu-id="ff40c-131">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>
