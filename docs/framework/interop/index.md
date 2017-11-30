---
title: "Взаимодействие с неуправляемым кодом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2db5b8c2425637e24086f54e8ef69b0e5aac3633
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="2ebbe-102">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="2ebbe-102">Interoperating with Unmanaged Code</span></span>
<span data-ttu-id="2ebbe-103">Платформа .NET Framework обеспечивает взаимодействие с COM-компонентами, службами COM+, внешними библиотеками типов и многими службами операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="2ebbe-104">Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="2ebbe-105">Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>  
  
 <span data-ttu-id="2ebbe-106">Код, выполняющийся под управлением среды выполнения, называется управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="2ebbe-107">И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="2ebbe-108">Примерами неуправляемого кода являются компоненты COM, интерфейсы ActiveX и функции Win32 API.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-108">COM components, ActiveX interfaces, and Win32 API functions are examples of unmanaged code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ebbe-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="2ebbe-109">In This Section</span></span>  
 [<span data-ttu-id="2ebbe-110">Разделы практических руководств, описывающие взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="2ebbe-110">Interoperating with Unmanaged Code How-to Topics</span></span>](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 <span data-ttu-id="2ebbe-111">Содержит ссылки на все разделы практического руководства в основной документации по взаимодействию с неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-111">Provides links to all How-to topics found in the conceptual documentation for interoperating with unmanaged code.</span></span>  
  
 [<span data-ttu-id="2ebbe-112">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ebbe-112">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="2ebbe-113">Описывает способы использования COM-компонентов в приложениях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-113">Describes how to use COM components from .NET Framework applications.</span></span>  
  
 [<span data-ttu-id="2ebbe-114">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="2ebbe-114">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="2ebbe-115">Описывает способы использования компонентов .NET Framework в приложениях COM.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-115">Describes how to use .NET Framework components from COM applications.</span></span>  
  
 [<span data-ttu-id="2ebbe-116">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="2ebbe-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="2ebbe-117">Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="2ebbe-118">Вопросы разработки для взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2ebbe-118">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 <span data-ttu-id="2ebbe-119">Приводятся советы по написанию кода встроенных COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-119">Provides tips for writing integrated COM components.</span></span>  
  
 [<span data-ttu-id="2ebbe-120">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2ebbe-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 <span data-ttu-id="2ebbe-121">Описывается маршалинг для COM-взаимодействия и вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-121">Describes marshaling for COM interop and platform invoke.</span></span>  
  
 [<span data-ttu-id="2ebbe-122">Практическое руководство. Сопоставление значений HRESULT и исключений</span><span class="sxs-lookup"><span data-stu-id="2ebbe-122">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 <span data-ttu-id="2ebbe-123">Описывает сопоставление исключений и значений HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-123">Describes the mapping between exceptions and HRESULTs.</span></span>  
  
 [<span data-ttu-id="2ebbe-124">Взаимодействие с помощью универсальных типов</span><span class="sxs-lookup"><span data-stu-id="2ebbe-124">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 <span data-ttu-id="2ebbe-125">Описывает поведение универсальных типов при использовании в COM-взаимодействии.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-125">Describes the behavior of generic types when used in COM interop.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2ebbe-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2ebbe-126">Related Sections</span></span>  
 [<span data-ttu-id="2ebbe-127">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="2ebbe-127">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="2ebbe-128">Приводятся ссылки на дополнительные сведения о включении COM-компонентов в разрабатываемое приложение .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ebbe-128">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>
