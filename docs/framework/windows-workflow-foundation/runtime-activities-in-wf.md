---
title: Действия времени выполнения в WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513039"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="f069d-102">Действия времени выполнения в WF</span><span class="sxs-lookup"><span data-stu-id="f069d-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="f069d-103"> содержит несколько предоставляемых системой действий для доступа к функциям среды выполнения рабочих процессов, например к функциям сохраняемости и завершения рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="f069d-103"> provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="f069d-104">Действие</span><span class="sxs-lookup"><span data-stu-id="f069d-104">Activity</span></span>|<span data-ttu-id="f069d-105">Описание</span><span class="sxs-lookup"><span data-stu-id="f069d-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="f069d-106">Явно запрашивает сохранение состояния рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f069d-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="f069d-107">Завершает выполнение экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f069d-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="f069d-108">Действие контейнера, препятствующее сохранению дочерних действий.</span><span class="sxs-lookup"><span data-stu-id="f069d-108">A container activity that prevents child activities from persisting.</span></span>|
