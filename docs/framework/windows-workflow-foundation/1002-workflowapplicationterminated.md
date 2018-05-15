---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="34ca0-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="34ca0-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="34ca0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="34ca0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34ca0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="34ca0-104">ID</span></span>|<span data-ttu-id="34ca0-105">1002</span><span class="sxs-lookup"><span data-stu-id="34ca0-105">1002</span></span>|  
|<span data-ttu-id="34ca0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="34ca0-106">Keywords</span></span>|<span data-ttu-id="34ca0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="34ca0-107">WFRuntime</span></span>|  
|<span data-ttu-id="34ca0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="34ca0-108">Level</span></span>|<span data-ttu-id="34ca0-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="34ca0-109">Information</span></span>|  
|<span data-ttu-id="34ca0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="34ca0-110">Channel</span></span>|<span data-ttu-id="34ca0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="34ca0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34ca0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="34ca0-112">Description</span></span>  
 <span data-ttu-id="34ca0-113">Указывает, что приложение рабочего процесса было остановлено в состоянии Faulted с исключением.</span><span class="sxs-lookup"><span data-stu-id="34ca0-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34ca0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="34ca0-114">Message</span></span>  
 <span data-ttu-id="34ca0-115">WorkflowApplication с идентификатором «%1» остановлено.</span><span class="sxs-lookup"><span data-stu-id="34ca0-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="34ca0-116">Был прерван в состоянии сбоя с исключением.</span><span class="sxs-lookup"><span data-stu-id="34ca0-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34ca0-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="34ca0-117">Details</span></span>  
  
|<span data-ttu-id="34ca0-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="34ca0-118">Data Item Name</span></span>|<span data-ttu-id="34ca0-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="34ca0-119">Data Item Type</span></span>|<span data-ttu-id="34ca0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="34ca0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34ca0-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="34ca0-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="34ca0-122">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="34ca0-122">The workflow application id</span></span>|  
|<span data-ttu-id="34ca0-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="34ca0-123">Exception</span></span>|`xs:string`|<span data-ttu-id="34ca0-124">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="34ca0-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="34ca0-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34ca0-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="34ca0-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="34ca0-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
