---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008633"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="2f1b5-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="2f1b5-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="2f1b5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2f1b5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f1b5-104">ID</span><span class="sxs-lookup"><span data-stu-id="2f1b5-104">ID</span></span>|<span data-ttu-id="2f1b5-105">1003</span><span class="sxs-lookup"><span data-stu-id="2f1b5-105">1003</span></span>|  
|<span data-ttu-id="2f1b5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2f1b5-106">Keywords</span></span>|<span data-ttu-id="2f1b5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2f1b5-107">WFRuntime</span></span>|  
|<span data-ttu-id="2f1b5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2f1b5-108">Level</span></span>|<span data-ttu-id="2f1b5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2f1b5-109">Information</span></span>|  
|<span data-ttu-id="2f1b5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2f1b5-110">Channel</span></span>|<span data-ttu-id="2f1b5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f1b5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f1b5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2f1b5-112">Description</span></span>  
 <span data-ttu-id="2f1b5-113">Указывает, что экземпляр рабочего процесса завершено в состоянии Canceled.</span><span class="sxs-lookup"><span data-stu-id="2f1b5-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f1b5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2f1b5-114">Message</span></span>  
 <span data-ttu-id="2f1b5-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Canceled.</span><span class="sxs-lookup"><span data-stu-id="2f1b5-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f1b5-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2f1b5-116">Details</span></span>  
  
|<span data-ttu-id="2f1b5-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f1b5-117">Data Item Name</span></span>|<span data-ttu-id="2f1b5-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2f1b5-118">Data Item Type</span></span>|<span data-ttu-id="2f1b5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2f1b5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f1b5-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f1b5-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2f1b5-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2f1b5-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="2f1b5-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="2f1b5-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2f1b5-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2f1b5-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
