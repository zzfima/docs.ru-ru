---
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 4c9ae5fd386fc93ea19578097aa4e0afdda527e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924128"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="b748a-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="b748a-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="b748a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b748a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b748a-104">ID</span><span class="sxs-lookup"><span data-stu-id="b748a-104">ID</span></span>|<span data-ttu-id="b748a-105">1104</span><span class="sxs-lookup"><span data-stu-id="b748a-105">1104</span></span>|  
|<span data-ttu-id="b748a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b748a-106">Keywords</span></span>|<span data-ttu-id="b748a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b748a-107">WFRuntime</span></span>|  
|<span data-ttu-id="b748a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b748a-108">Level</span></span>|<span data-ttu-id="b748a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b748a-109">Information</span></span>|  
|<span data-ttu-id="b748a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b748a-110">Channel</span></span>|<span data-ttu-id="b748a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b748a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b748a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b748a-112">Description</span></span>  
 <span data-ttu-id="b748a-113">Указывает, что действие рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="b748a-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b748a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b748a-114">Message</span></span>  
 <span data-ttu-id="b748a-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="b748a-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="b748a-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b748a-116">Details</span></span>  
  
|<span data-ttu-id="b748a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b748a-117">Data Item Name</span></span>|<span data-ttu-id="b748a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b748a-118">Data Item Type</span></span>|<span data-ttu-id="b748a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b748a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b748a-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="b748a-120">WorkflowInstanceId</span></span>|<span data-ttu-id="b748a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b748a-121">xs:string</span></span>|<span data-ttu-id="b748a-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b748a-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="b748a-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="b748a-123">AppDomain</span></span>|<span data-ttu-id="b748a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b748a-124">xs:string</span></span>|<span data-ttu-id="b748a-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b748a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
