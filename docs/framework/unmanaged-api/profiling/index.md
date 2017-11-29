---
title: "Профилирование (справочник по неуправляемым интерфейсам API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], profiling
- unmanaged API reference [.NET Framework], profiling
ms.assetid: 14c68e84-657e-49c2-aa8b-4978dbaf4454
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 26fa9471b46a7a963d66ebf0d5b3c6a0286ae640
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-unmanaged-api-reference"></a><span data-ttu-id="97171-102">Профилирование (справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="97171-102">Profiling (Unmanaged API Reference)</span></span>
<span data-ttu-id="97171-103">API профилирования позволяет профилировщику отслеживать выполнение программы с общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="97171-103">The profiling API enables a profiler to monitor a program's execution by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97171-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="97171-104">In This Section</span></span>  
 [<span data-ttu-id="97171-105">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="97171-105">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
 <span data-ttu-id="97171-106">Описание служб и интерфейсов, предоставляемых средой CLR для поддержки профилирования в среде .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97171-106">Describes the services and interfaces that the CLR provides to support profiling in the .NET Framework environment.</span></span>  
  
 [<span data-ttu-id="97171-107">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="97171-107">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 <span data-ttu-id="97171-108">В этом разделе описываются неуправляемые интерфейсы, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="97171-108">Describes the unmanaged interfaces that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="97171-109">Настройка среды профилирования</span><span class="sxs-lookup"><span data-stu-id="97171-109">Setting Up a Profiling Environment</span></span>](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)  
 <span data-ttu-id="97171-110">Описание действий, которые необходимо выполнить профилирование приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97171-110">Describes the steps you must take to profile a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="97171-111">Профилировщик среды CLR и приложений для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="97171-111">CLR Profilers and Windows Store Apps</span></span>](../../../../docs/framework/unmanaged-api/profiling/clr-profilers-and-windows-store-apps.md)  
 <span data-ttu-id="97171-112">Описывает, как перенести средства диагностики, которые используют API профилирования среды CLR для успешной работы с приложениями для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="97171-112">Discusses how to port diagnostic tools that consume the CLR Profiling API to work successfully with Windows Store apps.</span></span>  
  
 [<span data-ttu-id="97171-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span><span class="sxs-lookup"><span data-stu-id="97171-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span></span>](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)  
 <span data-ttu-id="97171-114">Документирует условия, при которых вызов метода возвращает `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span><span class="sxs-lookup"><span data-stu-id="97171-114">Documents the conditions under which a method call returns the `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span></span>  
  
 [<span data-ttu-id="97171-115">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="97171-115">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 <span data-ttu-id="97171-116">В этом разделе описываются неуправляемые глобальные статистические функции, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="97171-116">Describes the unmanaged global static functions that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="97171-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="97171-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 <span data-ttu-id="97171-118">В этом разделе описываются неуправляемые перечисления, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="97171-118">Describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="97171-119">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="97171-119">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 <span data-ttu-id="97171-120">В этом разделе описываются неуправляемые структуры, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="97171-120">Describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="97171-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="97171-121">Related Sections</span></span>  
 [<span data-ttu-id="97171-122">Пошаговое руководство. Выявление проблем с производительностью</span><span class="sxs-lookup"><span data-stu-id="97171-122">Walkthrough: Identifying Performance Problems</span></span>](/visualstudio/profiling/walkthrough-identifying-performance-problems)  
 <span data-ttu-id="97171-123">Объясняется, как использовать встроенные средства профилирования в Microsoft Visual Studio 2005 Team System.</span><span class="sxs-lookup"><span data-stu-id="97171-123">Explains how to use the built-in profiling tools in the Microsoft Visual Studio 2005 Team System.</span></span> <span data-ttu-id="97171-124">Эти средства предоставляют альтернативный подход к использованию API профилирования.</span><span class="sxs-lookup"><span data-stu-id="97171-124">These tools provide an alternative approach to using the profiling API.</span></span>
