---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dedb1dd389e2308ea8f70d71f057d17a45172517
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="30adf-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="30adf-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="30adf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="30adf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30adf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="30adf-104">ID</span></span>|<span data-ttu-id="30adf-105">1008</span><span class="sxs-lookup"><span data-stu-id="30adf-105">1008</span></span>|  
|<span data-ttu-id="30adf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="30adf-106">Keywords</span></span>|<span data-ttu-id="30adf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="30adf-107">WFRuntime</span></span>|  
|<span data-ttu-id="30adf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="30adf-108">Level</span></span>|<span data-ttu-id="30adf-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="30adf-109">Information</span></span>|  
|<span data-ttu-id="30adf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="30adf-110">Channel</span></span>|<span data-ttu-id="30adf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="30adf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30adf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="30adf-112">Description</span></span>  
 <span data-ttu-id="30adf-113">Указывает, что приложение рабочего процесса выгружено.</span><span class="sxs-lookup"><span data-stu-id="30adf-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30adf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="30adf-114">Message</span></span>  
 <span data-ttu-id="30adf-115">Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.</span><span class="sxs-lookup"><span data-stu-id="30adf-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30adf-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="30adf-116">Details</span></span>  
  
|<span data-ttu-id="30adf-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="30adf-117">Data Item Name</span></span>|<span data-ttu-id="30adf-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="30adf-118">Data Item Type</span></span>|<span data-ttu-id="30adf-119">Описание</span><span class="sxs-lookup"><span data-stu-id="30adf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30adf-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="30adf-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="30adf-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="30adf-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="30adf-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="30adf-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="30adf-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="30adf-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
