---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008646"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="f8d66-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="f8d66-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="f8d66-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f8d66-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8d66-104">ID</span><span class="sxs-lookup"><span data-stu-id="f8d66-104">ID</span></span>|<span data-ttu-id="f8d66-105">1001</span><span class="sxs-lookup"><span data-stu-id="f8d66-105">1001</span></span>|  
|<span data-ttu-id="f8d66-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f8d66-106">Keywords</span></span>|<span data-ttu-id="f8d66-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f8d66-107">WFRuntime</span></span>|  
|<span data-ttu-id="f8d66-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f8d66-108">Level</span></span>|<span data-ttu-id="f8d66-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f8d66-109">Information</span></span>|  
|<span data-ttu-id="f8d66-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f8d66-110">Channel</span></span>|<span data-ttu-id="f8d66-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f8d66-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f8d66-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f8d66-112">Description</span></span>  
 <span data-ttu-id="f8d66-113">Указывает, что приложение рабочего процесса завершено в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="f8d66-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f8d66-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f8d66-114">Message</span></span>  
 <span data-ttu-id="f8d66-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="f8d66-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f8d66-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f8d66-116">Details</span></span>  
  
|<span data-ttu-id="f8d66-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f8d66-117">Data Item Name</span></span>|<span data-ttu-id="f8d66-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f8d66-118">Data Item Type</span></span>|<span data-ttu-id="f8d66-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f8d66-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f8d66-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f8d66-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f8d66-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f8d66-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f8d66-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="f8d66-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f8d66-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f8d66-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
