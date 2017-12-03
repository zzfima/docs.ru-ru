---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2603621eb23747275e6db22a1743c5260967c6a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="05ebe-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="05ebe-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="05ebe-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="05ebe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05ebe-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="05ebe-104">ID</span></span>|<span data-ttu-id="05ebe-105">1005</span><span class="sxs-lookup"><span data-stu-id="05ebe-105">1005</span></span>|  
|<span data-ttu-id="05ebe-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="05ebe-106">Keywords</span></span>|<span data-ttu-id="05ebe-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="05ebe-107">WFRuntime</span></span>|  
|<span data-ttu-id="05ebe-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="05ebe-108">Level</span></span>|<span data-ttu-id="05ebe-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="05ebe-109">Information</span></span>|  
|<span data-ttu-id="05ebe-110">Канал</span><span class="sxs-lookup"><span data-stu-id="05ebe-110">Channel</span></span>|<span data-ttu-id="05ebe-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="05ebe-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="05ebe-112">Описание</span><span class="sxs-lookup"><span data-stu-id="05ebe-112">Description</span></span>  
 <span data-ttu-id="05ebe-113">Указывает, что приложение рабочего процесса простаивало.</span><span class="sxs-lookup"><span data-stu-id="05ebe-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="05ebe-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="05ebe-114">Message</span></span>  
 <span data-ttu-id="05ebe-115">WorkflowApplication с идентификатором «%1» перешло в состояние простоя.</span><span class="sxs-lookup"><span data-stu-id="05ebe-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="05ebe-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="05ebe-116">Details</span></span>  
  
|<span data-ttu-id="05ebe-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="05ebe-117">Data Item Name</span></span>|<span data-ttu-id="05ebe-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="05ebe-118">Data Item Type</span></span>|<span data-ttu-id="05ebe-119">Описание</span><span class="sxs-lookup"><span data-stu-id="05ebe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="05ebe-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="05ebe-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="05ebe-121">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="05ebe-121">The workflow application id</span></span>|  
|<span data-ttu-id="05ebe-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="05ebe-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="05ebe-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="05ebe-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
