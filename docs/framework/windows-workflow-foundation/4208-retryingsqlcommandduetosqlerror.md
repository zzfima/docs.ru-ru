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
ms.openlocfilehash: b3bfe7547fafb17503c972646d344263117d9d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="5e976-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="5e976-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="5e976-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5e976-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e976-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="5e976-104">ID</span></span>|<span data-ttu-id="5e976-105">4208</span><span class="sxs-lookup"><span data-stu-id="5e976-105">4208</span></span>|  
|<span data-ttu-id="5e976-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="5e976-106">Keywords</span></span>|<span data-ttu-id="5e976-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5e976-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5e976-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="5e976-108">Level</span></span>|<span data-ttu-id="5e976-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5e976-109">Information</span></span>|  
|<span data-ttu-id="5e976-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5e976-110">Channel</span></span>|<span data-ttu-id="5e976-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5e976-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5e976-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5e976-112">Description</span></span>  
 <span data-ttu-id="5e976-113">Указывает, что поставщик SQL повторяет команду SQL из-за ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="5e976-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5e976-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5e976-114">Message</span></span>  
 <span data-ttu-id="5e976-115">Выполняется повтор команды SQL из-за ошибки SQL с номером %1.</span><span class="sxs-lookup"><span data-stu-id="5e976-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5e976-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5e976-116">Details</span></span>  
  
|<span data-ttu-id="5e976-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5e976-117">Data Item Name</span></span>|<span data-ttu-id="5e976-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5e976-118">Data Item Type</span></span>|<span data-ttu-id="5e976-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5e976-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5e976-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="5e976-120">ErrorNumber</span></span>|<span data-ttu-id="5e976-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e976-121">xs:string</span></span>|<span data-ttu-id="5e976-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="5e976-122">The SQL error number.</span></span>|  
|<span data-ttu-id="5e976-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5e976-123">AppDomain</span></span>|<span data-ttu-id="5e976-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e976-124">xs:string</span></span>|<span data-ttu-id="5e976-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5e976-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
