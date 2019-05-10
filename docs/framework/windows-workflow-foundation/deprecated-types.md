---
title: Устаревшие типы в Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: c8325e60d708b53e1701a980355d5d2bf20e8a4b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644959"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="12f3c-102">Устаревшие типы в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="12f3c-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="12f3c-103">В .NET 4 команда разработки по рабочим процессам представила полностью новую подсистему рабочих процессов в пространстве имен <xref:System.Activities>.</span><span class="sxs-lookup"><span data-stu-id="12f3c-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="12f3c-104">С появлением бета-версии .NET 4.5 Мы отмечаем большинство типов в «WF 3» <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, и <xref:System.Workflow.Runtime> пространства имен, как устаревшие.</span><span class="sxs-lookup"><span data-stu-id="12f3c-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="12f3c-105">Устаревшие пространства имен и средства</span><span class="sxs-lookup"><span data-stu-id="12f3c-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="12f3c-106">Следующие сборки содержат один и более открытых типов, которые станут устаревшими.</span><span class="sxs-lookup"><span data-stu-id="12f3c-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
- <span data-ttu-id="12f3c-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="12f3c-107">System.Workflow.Activities.dll</span></span>  
  
- <span data-ttu-id="12f3c-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="12f3c-108">System.Workflow.ComponentModel.dll</span></span>  
  
- <span data-ttu-id="12f3c-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="12f3c-109">System.Workflow.Runtime.dll</span></span>  
  
- <span data-ttu-id="12f3c-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="12f3c-110">System.WorkflowServices.dll</span></span>  
  
- <span data-ttu-id="12f3c-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="12f3c-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
- <span data-ttu-id="12f3c-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="12f3c-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
- <span data-ttu-id="12f3c-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="12f3c-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="12f3c-114">В результате этого клиенты, использующие устаревшие API WF 3, увидят предупреждения при сборке с сообщением следующего вида:</span><span class="sxs-lookup"><span data-stu-id="12f3c-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="12f3c-115">**Предупреждение BC40000. X устарело: WF 3 являются устаревшими. Используйте WF 4.**</span><span class="sxs-lookup"><span data-stu-id="12f3c-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="12f3c-116">В одном из последующих выпусков (не в 4.5) типы будут удалены из .NET Framework, но временной промежуток до этого еще не определен.</span><span class="sxs-lookup"><span data-stu-id="12f3c-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="12f3c-117">Текущий шаг позволяет донести наши планы до клиентов и дает им достаточно времени для перехода на новую модель WF4.</span><span class="sxs-lookup"><span data-stu-id="12f3c-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="12f3c-118">Мы Конечно, продолжит поддерживать эти типы WF 3 в разделе [политики жизненного цикла поддержки Microsoft](https://aka.ms/MicrosoftSupportLifecycle).</span><span class="sxs-lookup"><span data-stu-id="12f3c-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](https://aka.ms/MicrosoftSupportLifecycle).</span></span> <span data-ttu-id="12f3c-119">Существующие приложения WF3 будет выполняться без проблем на .NET 4.5 и Visual Studio 2012 будет поддерживать новых и существующих решений на основе WF3.</span><span class="sxs-lookup"><span data-stu-id="12f3c-119">Existing WF3 applications will run without issue on .NET 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="12f3c-120">Основанные на правилах типы в пространстве имен <xref:System.Workflow.Activities.Rules>, не имеющие замены в WF 4.5, не устарели.</span><span class="sxs-lookup"><span data-stu-id="12f3c-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="12f3c-121">Клиенты, желающие перевести свои приложения на WF 4 будет найти полезную информацию в [руководство по миграции рабочего процесса 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="12f3c-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
