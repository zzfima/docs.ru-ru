---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008828"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="ab49c-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="ab49c-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ab49c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ab49c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab49c-104">ID</span><span class="sxs-lookup"><span data-stu-id="ab49c-104">ID</span></span>|<span data-ttu-id="ab49c-105">1027</span><span class="sxs-lookup"><span data-stu-id="ab49c-105">1027</span></span>|  
|<span data-ttu-id="ab49c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ab49c-106">Keywords</span></span>|<span data-ttu-id="ab49c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ab49c-107">WFRuntime</span></span>|  
|<span data-ttu-id="ab49c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ab49c-108">Level</span></span>|<span data-ttu-id="ab49c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ab49c-109">Verbose</span></span>|  
|<span data-ttu-id="ab49c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ab49c-110">Channel</span></span>|<span data-ttu-id="ab49c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ab49c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab49c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ab49c-112">Description</span></span>  
 <span data-ttu-id="ab49c-113">Указывает, что начинается выполнение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ab49c-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab49c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ab49c-114">Message</span></span>  
 <span data-ttu-id="ab49c-115">Начато выполнение TransactionContextWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="ab49c-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab49c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ab49c-116">Details</span></span>  
  
|<span data-ttu-id="ab49c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ab49c-117">Data Item Name</span></span>|<span data-ttu-id="ab49c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ab49c-118">Data Item Type</span></span>|<span data-ttu-id="ab49c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ab49c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab49c-120">Действие</span><span class="sxs-lookup"><span data-stu-id="ab49c-120">Activity</span></span>|<span data-ttu-id="ab49c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab49c-121">xs:string</span></span>|<span data-ttu-id="ab49c-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="ab49c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ab49c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ab49c-123">DisplayName</span></span>|<span data-ttu-id="ab49c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab49c-124">xs:string</span></span>|<span data-ttu-id="ab49c-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="ab49c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ab49c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ab49c-126">InstanceId</span></span>|<span data-ttu-id="ab49c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab49c-127">xs:string</span></span>|<span data-ttu-id="ab49c-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="ab49c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ab49c-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ab49c-129">AppDomain</span></span>|<span data-ttu-id="ab49c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab49c-130">xs:string</span></span>|<span data-ttu-id="ab49c-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ab49c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
