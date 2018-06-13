---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 3c981888b491f2797a431c2103ba3f5f0bd17046
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511177"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="3186a-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="3186a-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="3186a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3186a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3186a-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3186a-104">ID</span></span>|<span data-ttu-id="3186a-105">4206</span><span class="sxs-lookup"><span data-stu-id="3186a-105">4206</span></span>|  
|<span data-ttu-id="3186a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3186a-106">Keywords</span></span>|<span data-ttu-id="3186a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3186a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3186a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3186a-108">Level</span></span>|<span data-ttu-id="3186a-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="3186a-109">Error</span></span>|  
|<span data-ttu-id="3186a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3186a-110">Channel</span></span>|<span data-ttu-id="3186a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3186a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3186a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3186a-112">Description</span></span>  
 <span data-ttu-id="3186a-113">Указывает, что при попытке разблокировать экземпляр возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="3186a-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3186a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3186a-114">Message</span></span>  
 <span data-ttu-id="3186a-115">При попытке разблокировать экземпляр обнаружено исключение «%1».</span><span class="sxs-lookup"><span data-stu-id="3186a-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3186a-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3186a-116">Details</span></span>  
  
|<span data-ttu-id="3186a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3186a-117">Data Item Name</span></span>|<span data-ttu-id="3186a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3186a-118">Data Item Type</span></span>|<span data-ttu-id="3186a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3186a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3186a-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="3186a-120">ExceptionMessage</span></span>|<span data-ttu-id="3186a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3186a-121">xs:string</span></span>|<span data-ttu-id="3186a-122">Текст сообщения из исключения SQL.</span><span class="sxs-lookup"><span data-stu-id="3186a-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="3186a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3186a-123">AppDomain</span></span>|<span data-ttu-id="3186a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3186a-124">xs:string</span></span>|<span data-ttu-id="3186a-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3186a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
