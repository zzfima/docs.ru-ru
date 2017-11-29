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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 297b3ad9a677d28d12d1b00fdaeec8ec94842263
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="383c7-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="383c7-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="383c7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="383c7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="383c7-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="383c7-104">ID</span></span>|<span data-ttu-id="383c7-105">1008</span><span class="sxs-lookup"><span data-stu-id="383c7-105">1008</span></span>|  
|<span data-ttu-id="383c7-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="383c7-106">Keywords</span></span>|<span data-ttu-id="383c7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="383c7-107">WFRuntime</span></span>|  
|<span data-ttu-id="383c7-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="383c7-108">Level</span></span>|<span data-ttu-id="383c7-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="383c7-109">Information</span></span>|  
|<span data-ttu-id="383c7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="383c7-110">Channel</span></span>|<span data-ttu-id="383c7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="383c7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="383c7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="383c7-112">Description</span></span>  
 <span data-ttu-id="383c7-113">Указывает, что приложение рабочего процесса выгружено.</span><span class="sxs-lookup"><span data-stu-id="383c7-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="383c7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="383c7-114">Message</span></span>  
 <span data-ttu-id="383c7-115">Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.</span><span class="sxs-lookup"><span data-stu-id="383c7-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="383c7-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="383c7-116">Details</span></span>  
  
|<span data-ttu-id="383c7-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="383c7-117">Data Item Name</span></span>|<span data-ttu-id="383c7-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="383c7-118">Data Item Type</span></span>|<span data-ttu-id="383c7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="383c7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="383c7-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="383c7-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="383c7-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="383c7-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="383c7-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="383c7-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="383c7-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="383c7-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
