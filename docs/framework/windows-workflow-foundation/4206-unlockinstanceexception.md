---
title: 4206 - UnlockInstanceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 349844edb44e547a666f10c8d210d120ebf5a39f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="f99df-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="f99df-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="f99df-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f99df-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f99df-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f99df-104">ID</span></span>|<span data-ttu-id="f99df-105">4206</span><span class="sxs-lookup"><span data-stu-id="f99df-105">4206</span></span>|  
|<span data-ttu-id="f99df-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f99df-106">Keywords</span></span>|<span data-ttu-id="f99df-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f99df-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f99df-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f99df-108">Level</span></span>|<span data-ttu-id="f99df-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="f99df-109">Error</span></span>|  
|<span data-ttu-id="f99df-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f99df-110">Channel</span></span>|<span data-ttu-id="f99df-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f99df-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f99df-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f99df-112">Description</span></span>  
 <span data-ttu-id="f99df-113">Указывает, что при попытке разблокировать экземпляр возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="f99df-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f99df-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f99df-114">Message</span></span>  
 <span data-ttu-id="f99df-115">При попытке разблокировать экземпляр обнаружено исключение «%1».</span><span class="sxs-lookup"><span data-stu-id="f99df-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f99df-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f99df-116">Details</span></span>  
  
|<span data-ttu-id="f99df-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f99df-117">Data Item Name</span></span>|<span data-ttu-id="f99df-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f99df-118">Data Item Type</span></span>|<span data-ttu-id="f99df-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f99df-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f99df-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="f99df-120">ExceptionMessage</span></span>|<span data-ttu-id="f99df-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f99df-121">xs:string</span></span>|<span data-ttu-id="f99df-122">Текст сообщения из исключения SQL.</span><span class="sxs-lookup"><span data-stu-id="f99df-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="f99df-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f99df-123">AppDomain</span></span>|<span data-ttu-id="f99df-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f99df-124">xs:string</span></span>|<span data-ttu-id="f99df-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f99df-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
