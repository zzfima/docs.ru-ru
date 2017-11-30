---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54ef06c3aded628e18325b78f55e80e4470ecd01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="138dd-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="138dd-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="138dd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="138dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="138dd-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="138dd-104">ID</span></span>|<span data-ttu-id="138dd-105">1002</span><span class="sxs-lookup"><span data-stu-id="138dd-105">1002</span></span>|  
|<span data-ttu-id="138dd-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="138dd-106">Keywords</span></span>|<span data-ttu-id="138dd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="138dd-107">WFRuntime</span></span>|  
|<span data-ttu-id="138dd-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="138dd-108">Level</span></span>|<span data-ttu-id="138dd-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="138dd-109">Information</span></span>|  
|<span data-ttu-id="138dd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="138dd-110">Channel</span></span>|<span data-ttu-id="138dd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="138dd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="138dd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="138dd-112">Description</span></span>  
 <span data-ttu-id="138dd-113">Указывает, что приложение рабочего процесса было остановлено в состоянии Faulted с исключением.</span><span class="sxs-lookup"><span data-stu-id="138dd-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="138dd-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="138dd-114">Message</span></span>  
 <span data-ttu-id="138dd-115">WorkflowApplication с идентификатором «%1» остановлено.</span><span class="sxs-lookup"><span data-stu-id="138dd-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="138dd-116">Был прерван в состоянии сбоя с исключением.</span><span class="sxs-lookup"><span data-stu-id="138dd-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="138dd-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="138dd-117">Details</span></span>  
  
|<span data-ttu-id="138dd-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="138dd-118">Data Item Name</span></span>|<span data-ttu-id="138dd-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="138dd-119">Data Item Type</span></span>|<span data-ttu-id="138dd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="138dd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="138dd-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="138dd-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="138dd-122">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="138dd-122">The workflow application id</span></span>|  
|<span data-ttu-id="138dd-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="138dd-123">Exception</span></span>|`xs:string`|<span data-ttu-id="138dd-124">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="138dd-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="138dd-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="138dd-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="138dd-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="138dd-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
