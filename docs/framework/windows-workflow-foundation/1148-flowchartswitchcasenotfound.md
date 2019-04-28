---
title: 1148 - FlowchartSwitchCaseNotFound
ms.date: 03/30/2017
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
ms.openlocfilehash: 7e96b5b7652d404e6fdbe2c04c6a4069ca78f20f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009920"
---
# <a name="1148---flowchartswitchcasenotfound"></a><span data-ttu-id="a9f96-102">1148 - FlowchartSwitchCaseNotFound</span><span class="sxs-lookup"><span data-stu-id="a9f96-102">1148 - FlowchartSwitchCaseNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="a9f96-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a9f96-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9f96-104">ID</span><span class="sxs-lookup"><span data-stu-id="a9f96-104">ID</span></span>|<span data-ttu-id="a9f96-105">1148</span><span class="sxs-lookup"><span data-stu-id="a9f96-105">1148</span></span>|  
|<span data-ttu-id="a9f96-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a9f96-106">Keywords</span></span>|<span data-ttu-id="a9f96-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="a9f96-107">WFActivities</span></span>|  
|<span data-ttu-id="a9f96-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a9f96-108">Level</span></span>|<span data-ttu-id="a9f96-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a9f96-109">Information</span></span>|  
|<span data-ttu-id="a9f96-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a9f96-110">Channel</span></span>|<span data-ttu-id="a9f96-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a9f96-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a9f96-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a9f96-112">Description</span></span>  
 <span data-ttu-id="a9f96-113">Указывает, что в параметре блок-схемы не найден ни соответствующий вариант, ни вариант по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a9f96-113">Indicates that neither a matching case or a default case in a Flowchart switch could be found.</span></span> <span data-ttu-id="a9f96-114">Выполнение блок-схемы будет завершено.</span><span class="sxs-lookup"><span data-stu-id="a9f96-114">Flowchart execution will end.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a9f96-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a9f96-115">Message</span></span>  
 <span data-ttu-id="a9f96-116">Блок-схема «%1»/FlowSwitch - не удалось найти ни действие Case, ни действие Default Case, соответствующее результату выражения Expression.</span><span class="sxs-lookup"><span data-stu-id="a9f96-116">Flowchart '%1'/FlowSwitch - could find neither a Case activity nor a Default Case matching the Expression result.</span></span> <span data-ttu-id="a9f96-117">Выполнение блок-схемы будет завершено.</span><span class="sxs-lookup"><span data-stu-id="a9f96-117">Flowchart execution will end.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a9f96-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a9f96-118">Details</span></span>  
  
|<span data-ttu-id="a9f96-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a9f96-119">Data Item Name</span></span>|<span data-ttu-id="a9f96-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a9f96-120">Data Item Type</span></span>|<span data-ttu-id="a9f96-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a9f96-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a9f96-122">Блок-схема</span><span class="sxs-lookup"><span data-stu-id="a9f96-122">FlowChart</span></span>|<span data-ttu-id="a9f96-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9f96-123">xs:string</span></span>|<span data-ttu-id="a9f96-124">Отображаемое имя блок-схемы.</span><span class="sxs-lookup"><span data-stu-id="a9f96-124">The display name of the FlowChart.</span></span>|  
|<span data-ttu-id="a9f96-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="a9f96-125">AppDomain</span></span>|<span data-ttu-id="a9f96-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9f96-126">xs:string</span></span>|<span data-ttu-id="a9f96-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a9f96-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
