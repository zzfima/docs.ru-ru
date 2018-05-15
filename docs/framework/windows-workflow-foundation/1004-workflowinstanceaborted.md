---
title: 1004 ― WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d1eaf3cf107a6b5e244cc2d9372ee68d387ef6c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="590a3-102">1004 ― WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="590a3-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="590a3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="590a3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="590a3-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="590a3-104">ID</span></span>|<span data-ttu-id="590a3-105">1004</span><span class="sxs-lookup"><span data-stu-id="590a3-105">1004</span></span>|  
|<span data-ttu-id="590a3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="590a3-106">Keywords</span></span>|<span data-ttu-id="590a3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="590a3-107">WFRuntime</span></span>|  
|<span data-ttu-id="590a3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="590a3-108">Level</span></span>|<span data-ttu-id="590a3-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="590a3-109">Information</span></span>|  
|<span data-ttu-id="590a3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="590a3-110">Channel</span></span>|<span data-ttu-id="590a3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="590a3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="590a3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="590a3-112">Description</span></span>  
 <span data-ttu-id="590a3-113">Указывает, что экземпляр рабочего процесса был прерван с исключением.</span><span class="sxs-lookup"><span data-stu-id="590a3-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="590a3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="590a3-114">Message</span></span>  
 <span data-ttu-id="590a3-115">Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.</span><span class="sxs-lookup"><span data-stu-id="590a3-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="590a3-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="590a3-116">Details</span></span>  
  
|<span data-ttu-id="590a3-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="590a3-117">Data Item Name</span></span>|<span data-ttu-id="590a3-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="590a3-118">Data Item Type</span></span>|<span data-ttu-id="590a3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="590a3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="590a3-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="590a3-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="590a3-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="590a3-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="590a3-122">Исключение</span><span class="sxs-lookup"><span data-stu-id="590a3-122">Exception</span></span>|`xs:string`|<span data-ttu-id="590a3-123">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="590a3-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="590a3-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="590a3-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="590a3-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="590a3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
