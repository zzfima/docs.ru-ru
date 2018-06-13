---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509298"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="87a32-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="87a32-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="87a32-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="87a32-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87a32-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="87a32-104">ID</span></span>|<span data-ttu-id="87a32-105">1005</span><span class="sxs-lookup"><span data-stu-id="87a32-105">1005</span></span>|  
|<span data-ttu-id="87a32-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="87a32-106">Keywords</span></span>|<span data-ttu-id="87a32-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="87a32-107">WFRuntime</span></span>|  
|<span data-ttu-id="87a32-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="87a32-108">Level</span></span>|<span data-ttu-id="87a32-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="87a32-109">Information</span></span>|  
|<span data-ttu-id="87a32-110">Канал</span><span class="sxs-lookup"><span data-stu-id="87a32-110">Channel</span></span>|<span data-ttu-id="87a32-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="87a32-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87a32-112">Описание</span><span class="sxs-lookup"><span data-stu-id="87a32-112">Description</span></span>  
 <span data-ttu-id="87a32-113">Указывает, что приложение рабочего процесса простаивало.</span><span class="sxs-lookup"><span data-stu-id="87a32-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87a32-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="87a32-114">Message</span></span>  
 <span data-ttu-id="87a32-115">WorkflowApplication с идентификатором «%1» перешло в состояние простоя.</span><span class="sxs-lookup"><span data-stu-id="87a32-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87a32-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="87a32-116">Details</span></span>  
  
|<span data-ttu-id="87a32-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="87a32-117">Data Item Name</span></span>|<span data-ttu-id="87a32-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="87a32-118">Data Item Type</span></span>|<span data-ttu-id="87a32-119">Описание</span><span class="sxs-lookup"><span data-stu-id="87a32-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87a32-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="87a32-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="87a32-121">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="87a32-121">The workflow application id</span></span>|  
|<span data-ttu-id="87a32-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87a32-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="87a32-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="87a32-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
