---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008815"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="3cf85-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="3cf85-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3cf85-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3cf85-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cf85-104">ID</span><span class="sxs-lookup"><span data-stu-id="3cf85-104">ID</span></span>|<span data-ttu-id="3cf85-105">1028</span><span class="sxs-lookup"><span data-stu-id="3cf85-105">1028</span></span>|  
|<span data-ttu-id="3cf85-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3cf85-106">Keywords</span></span>|<span data-ttu-id="3cf85-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3cf85-107">WFRuntime</span></span>|  
|<span data-ttu-id="3cf85-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3cf85-108">Level</span></span>|<span data-ttu-id="3cf85-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="3cf85-109">Verbose</span></span>|  
|<span data-ttu-id="3cf85-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3cf85-110">Channel</span></span>|<span data-ttu-id="3cf85-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3cf85-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3cf85-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3cf85-112">Description</span></span>  
 <span data-ttu-id="3cf85-113">Указывает на завершение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="3cf85-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3cf85-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3cf85-114">Message</span></span>  
 <span data-ttu-id="3cf85-115">TransactionContextWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="3cf85-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3cf85-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3cf85-116">Details</span></span>  
  
|<span data-ttu-id="3cf85-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3cf85-117">Data Item Name</span></span>|<span data-ttu-id="3cf85-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3cf85-118">Data Item Type</span></span>|<span data-ttu-id="3cf85-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3cf85-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3cf85-120">Действие</span><span class="sxs-lookup"><span data-stu-id="3cf85-120">Activity</span></span>|<span data-ttu-id="3cf85-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cf85-121">xs:string</span></span>|<span data-ttu-id="3cf85-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="3cf85-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3cf85-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cf85-123">DisplayName</span></span>|<span data-ttu-id="3cf85-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cf85-124">xs:string</span></span>|<span data-ttu-id="3cf85-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="3cf85-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3cf85-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3cf85-126">InstanceId</span></span>|<span data-ttu-id="3cf85-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cf85-127">xs:string</span></span>|<span data-ttu-id="3cf85-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="3cf85-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3cf85-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="3cf85-129">AppDomain</span></span>|<span data-ttu-id="3cf85-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cf85-130">xs:string</span></span>|<span data-ttu-id="3cf85-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3cf85-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
