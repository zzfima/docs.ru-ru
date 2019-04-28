---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924193"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="9a31e-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="9a31e-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="9a31e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9a31e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a31e-104">ID</span><span class="sxs-lookup"><span data-stu-id="9a31e-104">ID</span></span>|<span data-ttu-id="9a31e-105">1041</span><span class="sxs-lookup"><span data-stu-id="9a31e-105">1041</span></span>|  
|<span data-ttu-id="9a31e-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9a31e-106">Keywords</span></span>|<span data-ttu-id="9a31e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9a31e-107">WFRuntime</span></span>|  
|<span data-ttu-id="9a31e-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9a31e-108">Level</span></span>|<span data-ttu-id="9a31e-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9a31e-109">Information</span></span>|  
|<span data-ttu-id="9a31e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9a31e-110">Channel</span></span>|<span data-ttu-id="9a31e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9a31e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9a31e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9a31e-112">Description</span></span>  
 <span data-ttu-id="9a31e-113">Указывает, что приложение рабочего процесса бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="9a31e-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="9a31e-114">Приложение рабочего процесса будет бездействующим или сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="9a31e-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9a31e-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9a31e-115">Message</span></span>  
 <span data-ttu-id="9a31e-116">WorkflowApplication с идентификатором: «%1» бездействует и сохраняемо.</span><span class="sxs-lookup"><span data-stu-id="9a31e-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="9a31e-117">Будет предпринято следующее действие: %2.</span><span class="sxs-lookup"><span data-stu-id="9a31e-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9a31e-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9a31e-118">Details</span></span>  
  
|<span data-ttu-id="9a31e-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9a31e-119">Data Item Name</span></span>|<span data-ttu-id="9a31e-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9a31e-120">Data Item Type</span></span>|<span data-ttu-id="9a31e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9a31e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9a31e-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="9a31e-122">WorkflowApplicationId</span></span>|<span data-ttu-id="9a31e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a31e-123">xs:string</span></span>|<span data-ttu-id="9a31e-124">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9a31e-124">The workflow application id</span></span>|  
|<span data-ttu-id="9a31e-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="9a31e-125">ActionTaken</span></span>|<span data-ttu-id="9a31e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a31e-126">xs:string</span></span>|<span data-ttu-id="9a31e-127">Действие, которое будет выполняться в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9a31e-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="9a31e-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="9a31e-128">AppDomain</span></span>|<span data-ttu-id="9a31e-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a31e-129">xs:string</span></span>|<span data-ttu-id="9a31e-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9a31e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
