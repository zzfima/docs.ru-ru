---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008659"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="b4baa-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="b4baa-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="b4baa-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b4baa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4baa-104">ID</span><span class="sxs-lookup"><span data-stu-id="b4baa-104">ID</span></span>|<span data-ttu-id="b4baa-105">1002</span><span class="sxs-lookup"><span data-stu-id="b4baa-105">1002</span></span>|  
|<span data-ttu-id="b4baa-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b4baa-106">Keywords</span></span>|<span data-ttu-id="b4baa-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b4baa-107">WFRuntime</span></span>|  
|<span data-ttu-id="b4baa-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b4baa-108">Level</span></span>|<span data-ttu-id="b4baa-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b4baa-109">Information</span></span>|  
|<span data-ttu-id="b4baa-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b4baa-110">Channel</span></span>|<span data-ttu-id="b4baa-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b4baa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4baa-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b4baa-112">Description</span></span>  
 <span data-ttu-id="b4baa-113">Указывает, что приложение рабочего процесса было остановлено в состоянии Faulted с исключением.</span><span class="sxs-lookup"><span data-stu-id="b4baa-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4baa-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b4baa-114">Message</span></span>  
 <span data-ttu-id="b4baa-115">WorkflowApplication с идентификатором «%1» остановлено.</span><span class="sxs-lookup"><span data-stu-id="b4baa-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="b4baa-116">Был прерван в состоянии сбоя с исключением.</span><span class="sxs-lookup"><span data-stu-id="b4baa-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4baa-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b4baa-117">Details</span></span>  
  
|<span data-ttu-id="b4baa-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b4baa-118">Data Item Name</span></span>|<span data-ttu-id="b4baa-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b4baa-119">Data Item Type</span></span>|<span data-ttu-id="b4baa-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b4baa-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4baa-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="b4baa-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="b4baa-122">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b4baa-122">The workflow application id</span></span>|  
|<span data-ttu-id="b4baa-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="b4baa-123">Exception</span></span>|`xs:string`|<span data-ttu-id="b4baa-124">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="b4baa-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="b4baa-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="b4baa-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b4baa-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b4baa-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
