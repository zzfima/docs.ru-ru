---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 3c981888b491f2797a431c2103ba3f5f0bd17046
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774326"
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="ca170-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="ca170-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="ca170-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ca170-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca170-104">ID</span><span class="sxs-lookup"><span data-stu-id="ca170-104">ID</span></span>|<span data-ttu-id="ca170-105">4206</span><span class="sxs-lookup"><span data-stu-id="ca170-105">4206</span></span>|  
|<span data-ttu-id="ca170-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ca170-106">Keywords</span></span>|<span data-ttu-id="ca170-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="ca170-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="ca170-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ca170-108">Level</span></span>|<span data-ttu-id="ca170-109">Error</span><span class="sxs-lookup"><span data-stu-id="ca170-109">Error</span></span>|  
|<span data-ttu-id="ca170-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ca170-110">Channel</span></span>|<span data-ttu-id="ca170-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ca170-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ca170-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ca170-112">Description</span></span>  
 <span data-ttu-id="ca170-113">Указывает, что при попытке разблокировать экземпляр возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="ca170-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ca170-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ca170-114">Message</span></span>  
 <span data-ttu-id="ca170-115">При попытке разблокировать экземпляр обнаружено исключение «%1».</span><span class="sxs-lookup"><span data-stu-id="ca170-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ca170-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ca170-116">Details</span></span>  
  
|<span data-ttu-id="ca170-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ca170-117">Data Item Name</span></span>|<span data-ttu-id="ca170-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ca170-118">Data Item Type</span></span>|<span data-ttu-id="ca170-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ca170-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ca170-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="ca170-120">ExceptionMessage</span></span>|<span data-ttu-id="ca170-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ca170-121">xs:string</span></span>|<span data-ttu-id="ca170-122">Текст сообщения из исключения SQL.</span><span class="sxs-lookup"><span data-stu-id="ca170-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="ca170-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ca170-123">AppDomain</span></span>|<span data-ttu-id="ca170-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ca170-124">xs:string</span></span>|<span data-ttu-id="ca170-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ca170-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
