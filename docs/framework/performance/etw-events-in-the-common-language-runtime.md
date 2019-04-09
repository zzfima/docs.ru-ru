---
title: События в среде CLR (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d059a5d4df402b309f628bf3e9393114c4cdeec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191397"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="583d4-102">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="583d4-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="583d4-103">В общеязыковой среде выполнения (CLR) реализован полезный механизм трассировки событий (ETW), который позволяет получать диагностические сведения для широкого спектра событий отладки и профилирования.</span><span class="sxs-lookup"><span data-stu-id="583d4-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="583d4-104">События трассировки событий Windows в среде CLR используют систему трассировки Windows ETW, дополняя существующие средства профилирования и отладки, реализованные в общеязыковой среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="583d4-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="583d4-105">Дополнительные сведения о трассировке событий Windows см. в статье [Улучшение отладки и настройки производительности с помощью ETW](https://go.microsoft.com/fwlink/?LinkID=161142) библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="583d4-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="583d4-106">Сведения о программе Xperf можно найти в записи [Windows Performance Toolkit — Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) блога NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="583d4-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="583d4-107">Для всех событий, описанных в разделах, посвященных событиям, требуется [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="583d4-107">The [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="583d4-108">Минимальный поддерживаемый клиент — операционная система Windows Vista; минимальный поддерживаемый сервер — Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="583d4-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="583d4-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="583d4-109">In This Section</span></span>  
 [<span data-ttu-id="583d4-110">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="583d4-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="583d4-111">Описывает средства и команды для захвата и просмотра событий трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="583d4-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="583d4-112">Поставщики ETW среды CLR</span><span class="sxs-lookup"><span data-stu-id="583d4-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="583d4-113">Содержит сведения о поставщиках среды выполнения и очистки, а также о том, как использовать их для сбора данных трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="583d4-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="583d4-114">Ключевые слова и уровни среды CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="583d4-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="583d4-115">Описывает ключевые слова для поставщиков среды выполнения и очистки, которые обеспечивают фильтрацию событий по категориям.</span><span class="sxs-lookup"><span data-stu-id="583d4-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="583d4-116">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="583d4-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="583d4-117">Содержит подробные сведения о событиях трассировки событий Windows в среде CLR, а также соответствующих ключевых словах, уровнях и данных событий.</span><span class="sxs-lookup"><span data-stu-id="583d4-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583d4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="583d4-118">See also</span></span>

- [<span data-ttu-id="583d4-119">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="583d4-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
