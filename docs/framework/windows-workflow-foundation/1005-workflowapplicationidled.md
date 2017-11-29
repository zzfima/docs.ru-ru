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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42d22a7187adc712c0f236111cecac89dd59e2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="847ac-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="847ac-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="847ac-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="847ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="847ac-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="847ac-104">ID</span></span>|<span data-ttu-id="847ac-105">1005</span><span class="sxs-lookup"><span data-stu-id="847ac-105">1005</span></span>|  
|<span data-ttu-id="847ac-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="847ac-106">Keywords</span></span>|<span data-ttu-id="847ac-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="847ac-107">WFRuntime</span></span>|  
|<span data-ttu-id="847ac-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="847ac-108">Level</span></span>|<span data-ttu-id="847ac-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="847ac-109">Information</span></span>|  
|<span data-ttu-id="847ac-110">Канал</span><span class="sxs-lookup"><span data-stu-id="847ac-110">Channel</span></span>|<span data-ttu-id="847ac-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="847ac-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="847ac-112">Описание</span><span class="sxs-lookup"><span data-stu-id="847ac-112">Description</span></span>  
 <span data-ttu-id="847ac-113">Указывает, что приложение рабочего процесса простаивало.</span><span class="sxs-lookup"><span data-stu-id="847ac-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="847ac-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="847ac-114">Message</span></span>  
 <span data-ttu-id="847ac-115">WorkflowApplication с идентификатором «%1» перешло в состояние простоя.</span><span class="sxs-lookup"><span data-stu-id="847ac-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="847ac-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="847ac-116">Details</span></span>  
  
|<span data-ttu-id="847ac-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="847ac-117">Data Item Name</span></span>|<span data-ttu-id="847ac-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="847ac-118">Data Item Type</span></span>|<span data-ttu-id="847ac-119">Описание</span><span class="sxs-lookup"><span data-stu-id="847ac-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="847ac-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="847ac-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="847ac-121">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="847ac-121">The workflow application id</span></span>|  
|<span data-ttu-id="847ac-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="847ac-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="847ac-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="847ac-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
