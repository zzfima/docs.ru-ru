---
title: 1101 - WorkflowActivityStart
ms.date: 03/30/2017
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
ms.openlocfilehash: 1e6db97284b7ca83d532166d96d7a42df0a51091
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924154"
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="b1952-102">1101 - WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="b1952-102">1101 - WorkflowActivityStart</span></span>
## <a name="properties"></a><span data-ttu-id="b1952-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b1952-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1952-104">ID</span><span class="sxs-lookup"><span data-stu-id="b1952-104">ID</span></span>|<span data-ttu-id="b1952-105">1101</span><span class="sxs-lookup"><span data-stu-id="b1952-105">1101</span></span>|  
|<span data-ttu-id="b1952-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b1952-106">Keywords</span></span>|<span data-ttu-id="b1952-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b1952-107">WFRuntime</span></span>|  
|<span data-ttu-id="b1952-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b1952-108">Level</span></span>|<span data-ttu-id="b1952-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b1952-109">Information</span></span>|  
|<span data-ttu-id="b1952-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b1952-110">Channel</span></span>|<span data-ttu-id="b1952-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b1952-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1952-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b1952-112">Description</span></span>  
 <span data-ttu-id="b1952-113">Указывает, что началось действие рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b1952-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1952-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b1952-114">Message</span></span>  
 <span data-ttu-id="b1952-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="b1952-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1952-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b1952-116">Details</span></span>  
  
|<span data-ttu-id="b1952-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b1952-117">Data Item Name</span></span>|<span data-ttu-id="b1952-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b1952-118">Data Item Type</span></span>|<span data-ttu-id="b1952-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b1952-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1952-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="b1952-120">WorkflowInstanceId</span></span>|<span data-ttu-id="b1952-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1952-121">xs:string</span></span>|<span data-ttu-id="b1952-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b1952-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="b1952-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="b1952-123">AppDomain</span></span>|<span data-ttu-id="b1952-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1952-124">xs:string</span></span>|<span data-ttu-id="b1952-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b1952-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
