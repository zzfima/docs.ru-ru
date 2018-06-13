---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509565"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="9f57f-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="9f57f-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="9f57f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9f57f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f57f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9f57f-104">ID</span></span>|<span data-ttu-id="9f57f-105">1008</span><span class="sxs-lookup"><span data-stu-id="9f57f-105">1008</span></span>|  
|<span data-ttu-id="9f57f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9f57f-106">Keywords</span></span>|<span data-ttu-id="9f57f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9f57f-107">WFRuntime</span></span>|  
|<span data-ttu-id="9f57f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9f57f-108">Level</span></span>|<span data-ttu-id="9f57f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9f57f-109">Information</span></span>|  
|<span data-ttu-id="9f57f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9f57f-110">Channel</span></span>|<span data-ttu-id="9f57f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9f57f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9f57f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9f57f-112">Description</span></span>  
 <span data-ttu-id="9f57f-113">Указывает, что приложение рабочего процесса выгружено.</span><span class="sxs-lookup"><span data-stu-id="9f57f-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9f57f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9f57f-114">Message</span></span>  
 <span data-ttu-id="9f57f-115">Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.</span><span class="sxs-lookup"><span data-stu-id="9f57f-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9f57f-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9f57f-116">Details</span></span>  
  
|<span data-ttu-id="9f57f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9f57f-117">Data Item Name</span></span>|<span data-ttu-id="9f57f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9f57f-118">Data Item Type</span></span>|<span data-ttu-id="9f57f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9f57f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9f57f-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="9f57f-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="9f57f-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9f57f-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="9f57f-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9f57f-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9f57f-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9f57f-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
