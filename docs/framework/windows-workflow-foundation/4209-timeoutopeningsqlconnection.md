---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774274"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="f2e29-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="f2e29-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="f2e29-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f2e29-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2e29-104">ID</span><span class="sxs-lookup"><span data-stu-id="f2e29-104">ID</span></span>|<span data-ttu-id="f2e29-105">4209</span><span class="sxs-lookup"><span data-stu-id="f2e29-105">4209</span></span>|  
|<span data-ttu-id="f2e29-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f2e29-106">Keywords</span></span>|<span data-ttu-id="f2e29-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f2e29-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f2e29-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f2e29-108">Level</span></span>|<span data-ttu-id="f2e29-109">Error</span><span class="sxs-lookup"><span data-stu-id="f2e29-109">Error</span></span>|  
|<span data-ttu-id="f2e29-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f2e29-110">Channel</span></span>|<span data-ttu-id="f2e29-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f2e29-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2e29-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f2e29-112">Description</span></span>  
 <span data-ttu-id="f2e29-113">Указывает, что при попытке открыть соединение SQL превышено время ожидания.</span><span class="sxs-lookup"><span data-stu-id="f2e29-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2e29-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f2e29-114">Message</span></span>  
 <span data-ttu-id="f2e29-115">Истекло время ожидания при открытии соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="f2e29-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="f2e29-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="f2e29-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="f2e29-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f2e29-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2e29-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f2e29-118">Details</span></span>  
  
|<span data-ttu-id="f2e29-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f2e29-119">Data Item Name</span></span>|<span data-ttu-id="f2e29-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f2e29-120">Data Item Type</span></span>|<span data-ttu-id="f2e29-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f2e29-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2e29-122">Время ожидания</span><span class="sxs-lookup"><span data-stu-id="f2e29-122">Timeout</span></span>|<span data-ttu-id="f2e29-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2e29-123">xs:string</span></span>|<span data-ttu-id="f2e29-124">Значение времени ожидания для открытия соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="f2e29-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="f2e29-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="f2e29-125">AppDomain</span></span>|<span data-ttu-id="f2e29-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2e29-126">xs:string</span></span>|<span data-ttu-id="f2e29-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f2e29-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
