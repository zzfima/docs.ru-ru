---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924713"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="60d86-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="60d86-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="60d86-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="60d86-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60d86-104">ID</span><span class="sxs-lookup"><span data-stu-id="60d86-104">ID</span></span>|<span data-ttu-id="60d86-105">1006</span><span class="sxs-lookup"><span data-stu-id="60d86-105">1006</span></span>|  
|<span data-ttu-id="60d86-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="60d86-106">Keywords</span></span>|<span data-ttu-id="60d86-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="60d86-107">WFRuntime</span></span>|  
|<span data-ttu-id="60d86-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="60d86-108">Level</span></span>|<span data-ttu-id="60d86-109">Error</span><span class="sxs-lookup"><span data-stu-id="60d86-109">Error</span></span>|  
|<span data-ttu-id="60d86-110">Канал</span><span class="sxs-lookup"><span data-stu-id="60d86-110">Channel</span></span>|<span data-ttu-id="60d86-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="60d86-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60d86-112">Описание</span><span class="sxs-lookup"><span data-stu-id="60d86-112">Description</span></span>  
 <span data-ttu-id="60d86-113">Указывает, что приложение рабочего процесса обнаружило необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="60d86-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60d86-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="60d86-114">Message</span></span>  
 <span data-ttu-id="60d86-115">Элемент WorkflowInstance с идентификатором: «%1» обнаружил необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="60d86-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="60d86-116">Возникло исключение из действия «%2», DisplayName: «%3».</span><span class="sxs-lookup"><span data-stu-id="60d86-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="60d86-117">Будет предпринято следующее действие: %4.</span><span class="sxs-lookup"><span data-stu-id="60d86-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60d86-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="60d86-118">Details</span></span>  
  
|<span data-ttu-id="60d86-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="60d86-119">Data Item Name</span></span>|<span data-ttu-id="60d86-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="60d86-120">Data Item Type</span></span>|<span data-ttu-id="60d86-121">Описание</span><span class="sxs-lookup"><span data-stu-id="60d86-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60d86-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="60d86-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="60d86-123">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="60d86-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="60d86-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="60d86-124">Exception</span></span>|`xs:string`|<span data-ttu-id="60d86-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="60d86-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="60d86-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="60d86-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="60d86-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="60d86-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
