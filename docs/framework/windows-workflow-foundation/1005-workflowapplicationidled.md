---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008607"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="e1905-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="e1905-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="e1905-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e1905-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1905-104">ID</span><span class="sxs-lookup"><span data-stu-id="e1905-104">ID</span></span>|<span data-ttu-id="e1905-105">1005</span><span class="sxs-lookup"><span data-stu-id="e1905-105">1005</span></span>|  
|<span data-ttu-id="e1905-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e1905-106">Keywords</span></span>|<span data-ttu-id="e1905-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e1905-107">WFRuntime</span></span>|  
|<span data-ttu-id="e1905-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e1905-108">Level</span></span>|<span data-ttu-id="e1905-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e1905-109">Information</span></span>|  
|<span data-ttu-id="e1905-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e1905-110">Channel</span></span>|<span data-ttu-id="e1905-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e1905-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1905-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e1905-112">Description</span></span>  
 <span data-ttu-id="e1905-113">Указывает, что приложение рабочего процесса простаивало.</span><span class="sxs-lookup"><span data-stu-id="e1905-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1905-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e1905-114">Message</span></span>  
 <span data-ttu-id="e1905-115">WorkflowApplication с идентификатором «%1» перешло в состояние простоя.</span><span class="sxs-lookup"><span data-stu-id="e1905-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1905-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e1905-116">Details</span></span>  
  
|<span data-ttu-id="e1905-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e1905-117">Data Item Name</span></span>|<span data-ttu-id="e1905-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e1905-118">Data Item Type</span></span>|<span data-ttu-id="e1905-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e1905-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1905-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1905-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="e1905-121">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e1905-121">The workflow application id</span></span>|  
|<span data-ttu-id="e1905-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="e1905-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e1905-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1905-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
