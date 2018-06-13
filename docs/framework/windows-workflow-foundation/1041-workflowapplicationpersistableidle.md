---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509671"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="9bc50-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="9bc50-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="9bc50-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9bc50-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9bc50-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9bc50-104">ID</span></span>|<span data-ttu-id="9bc50-105">1041</span><span class="sxs-lookup"><span data-stu-id="9bc50-105">1041</span></span>|  
|<span data-ttu-id="9bc50-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9bc50-106">Keywords</span></span>|<span data-ttu-id="9bc50-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9bc50-107">WFRuntime</span></span>|  
|<span data-ttu-id="9bc50-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9bc50-108">Level</span></span>|<span data-ttu-id="9bc50-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9bc50-109">Information</span></span>|  
|<span data-ttu-id="9bc50-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9bc50-110">Channel</span></span>|<span data-ttu-id="9bc50-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9bc50-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9bc50-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9bc50-112">Description</span></span>  
 <span data-ttu-id="9bc50-113">Указывает, что приложение рабочего процесса бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="9bc50-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="9bc50-114">Приложение рабочего процесса будет бездействующим или сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="9bc50-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9bc50-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9bc50-115">Message</span></span>  
 <span data-ttu-id="9bc50-116">WorkflowApplication с идентификатором: «%1» бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="9bc50-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="9bc50-117">Будут выполнены следующие действия: %2.</span><span class="sxs-lookup"><span data-stu-id="9bc50-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9bc50-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9bc50-118">Details</span></span>  
  
|<span data-ttu-id="9bc50-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9bc50-119">Data Item Name</span></span>|<span data-ttu-id="9bc50-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9bc50-120">Data Item Type</span></span>|<span data-ttu-id="9bc50-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9bc50-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9bc50-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="9bc50-122">WorkflowApplicationId</span></span>|<span data-ttu-id="9bc50-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="9bc50-123">xs:string</span></span>|<span data-ttu-id="9bc50-124">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9bc50-124">The workflow application id</span></span>|  
|<span data-ttu-id="9bc50-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="9bc50-125">ActionTaken</span></span>|<span data-ttu-id="9bc50-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9bc50-126">xs:string</span></span>|<span data-ttu-id="9bc50-127">Действие, которое будет выполняться в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9bc50-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="9bc50-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9bc50-128">AppDomain</span></span>|<span data-ttu-id="9bc50-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="9bc50-129">xs:string</span></span>|<span data-ttu-id="9bc50-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9bc50-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
