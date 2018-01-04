---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51374a25ee11b3344e950670cc7882db42d39779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="4c699-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="4c699-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="4c699-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4c699-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c699-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4c699-104">ID</span></span>|<span data-ttu-id="4c699-105">4208</span><span class="sxs-lookup"><span data-stu-id="4c699-105">4208</span></span>|  
|<span data-ttu-id="4c699-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4c699-106">Keywords</span></span>|<span data-ttu-id="4c699-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="4c699-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="4c699-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4c699-108">Level</span></span>|<span data-ttu-id="4c699-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="4c699-109">Information</span></span>|  
|<span data-ttu-id="4c699-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4c699-110">Channel</span></span>|<span data-ttu-id="4c699-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4c699-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4c699-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4c699-112">Description</span></span>  
 <span data-ttu-id="4c699-113">Указывает, что поставщик SQL повторяет команду SQL из-за ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="4c699-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4c699-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4c699-114">Message</span></span>  
 <span data-ttu-id="4c699-115">Выполняется повтор команды SQL из-за ошибки SQL с номером %1.</span><span class="sxs-lookup"><span data-stu-id="4c699-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c699-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4c699-116">Details</span></span>  
  
|<span data-ttu-id="4c699-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4c699-117">Data Item Name</span></span>|<span data-ttu-id="4c699-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4c699-118">Data Item Type</span></span>|<span data-ttu-id="4c699-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4c699-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4c699-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="4c699-120">ErrorNumber</span></span>|<span data-ttu-id="4c699-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c699-121">xs:string</span></span>|<span data-ttu-id="4c699-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="4c699-122">The SQL error number.</span></span>|  
|<span data-ttu-id="4c699-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4c699-123">AppDomain</span></span>|<span data-ttu-id="4c699-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4c699-124">xs:string</span></span>|<span data-ttu-id="4c699-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4c699-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
