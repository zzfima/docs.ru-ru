---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925233"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="a492c-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="a492c-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="a492c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a492c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a492c-104">ID</span><span class="sxs-lookup"><span data-stu-id="a492c-104">ID</span></span>|<span data-ttu-id="a492c-105">1008</span><span class="sxs-lookup"><span data-stu-id="a492c-105">1008</span></span>|  
|<span data-ttu-id="a492c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a492c-106">Keywords</span></span>|<span data-ttu-id="a492c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a492c-107">WFRuntime</span></span>|  
|<span data-ttu-id="a492c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a492c-108">Level</span></span>|<span data-ttu-id="a492c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a492c-109">Information</span></span>|  
|<span data-ttu-id="a492c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a492c-110">Channel</span></span>|<span data-ttu-id="a492c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a492c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a492c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a492c-112">Description</span></span>  
 <span data-ttu-id="a492c-113">Указывает, что приложение рабочего процесса выгружено.</span><span class="sxs-lookup"><span data-stu-id="a492c-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a492c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a492c-114">Message</span></span>  
 <span data-ttu-id="a492c-115">Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.</span><span class="sxs-lookup"><span data-stu-id="a492c-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a492c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a492c-116">Details</span></span>  
  
|<span data-ttu-id="a492c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a492c-117">Data Item Name</span></span>|<span data-ttu-id="a492c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a492c-118">Data Item Type</span></span>|<span data-ttu-id="a492c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a492c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a492c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a492c-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a492c-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a492c-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a492c-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="a492c-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a492c-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a492c-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
