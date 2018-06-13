---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509799"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="38e2b-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="38e2b-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="38e2b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="38e2b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38e2b-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="38e2b-104">ID</span></span>|<span data-ttu-id="38e2b-105">1001</span><span class="sxs-lookup"><span data-stu-id="38e2b-105">1001</span></span>|  
|<span data-ttu-id="38e2b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="38e2b-106">Keywords</span></span>|<span data-ttu-id="38e2b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="38e2b-107">WFRuntime</span></span>|  
|<span data-ttu-id="38e2b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="38e2b-108">Level</span></span>|<span data-ttu-id="38e2b-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="38e2b-109">Information</span></span>|  
|<span data-ttu-id="38e2b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="38e2b-110">Channel</span></span>|<span data-ttu-id="38e2b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="38e2b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38e2b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="38e2b-112">Description</span></span>  
 <span data-ttu-id="38e2b-113">Указывает, что приложение рабочего процесса завершено в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="38e2b-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="38e2b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="38e2b-114">Message</span></span>  
 <span data-ttu-id="38e2b-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="38e2b-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="38e2b-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="38e2b-116">Details</span></span>  
  
|<span data-ttu-id="38e2b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="38e2b-117">Data Item Name</span></span>|<span data-ttu-id="38e2b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="38e2b-118">Data Item Type</span></span>|<span data-ttu-id="38e2b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="38e2b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="38e2b-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="38e2b-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="38e2b-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="38e2b-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="38e2b-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="38e2b-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="38e2b-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="38e2b-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
