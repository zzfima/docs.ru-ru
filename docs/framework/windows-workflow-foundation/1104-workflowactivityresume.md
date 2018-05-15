---
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 4c9ae5fd386fc93ea19578097aa4e0afdda527e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="48bba-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="48bba-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="48bba-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="48bba-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48bba-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="48bba-104">ID</span></span>|<span data-ttu-id="48bba-105">1104</span><span class="sxs-lookup"><span data-stu-id="48bba-105">1104</span></span>|  
|<span data-ttu-id="48bba-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="48bba-106">Keywords</span></span>|<span data-ttu-id="48bba-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48bba-107">WFRuntime</span></span>|  
|<span data-ttu-id="48bba-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="48bba-108">Level</span></span>|<span data-ttu-id="48bba-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="48bba-109">Information</span></span>|  
|<span data-ttu-id="48bba-110">Канал</span><span class="sxs-lookup"><span data-stu-id="48bba-110">Channel</span></span>|<span data-ttu-id="48bba-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48bba-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48bba-112">Описание</span><span class="sxs-lookup"><span data-stu-id="48bba-112">Description</span></span>  
 <span data-ttu-id="48bba-113">Указывает, что действие рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="48bba-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48bba-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="48bba-114">Message</span></span>  
 <span data-ttu-id="48bba-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="48bba-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="48bba-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="48bba-116">Details</span></span>  
  
|<span data-ttu-id="48bba-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="48bba-117">Data Item Name</span></span>|<span data-ttu-id="48bba-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="48bba-118">Data Item Type</span></span>|<span data-ttu-id="48bba-119">Описание</span><span class="sxs-lookup"><span data-stu-id="48bba-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48bba-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="48bba-120">WorkflowInstanceId</span></span>|<span data-ttu-id="48bba-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="48bba-121">xs:string</span></span>|<span data-ttu-id="48bba-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="48bba-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="48bba-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48bba-123">AppDomain</span></span>|<span data-ttu-id="48bba-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="48bba-124">xs:string</span></span>|<span data-ttu-id="48bba-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="48bba-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
