---
title: 4210 - SqlExceptionCaught
ms.date: 03/30/2017
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
ms.openlocfilehash: 2493014e80e79ac2935c1bcc685147a74e48fb47
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774261"
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="20ff3-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="20ff3-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="20ff3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="20ff3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20ff3-104">ID</span><span class="sxs-lookup"><span data-stu-id="20ff3-104">ID</span></span>|<span data-ttu-id="20ff3-105">4210</span><span class="sxs-lookup"><span data-stu-id="20ff3-105">4210</span></span>|  
|<span data-ttu-id="20ff3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="20ff3-106">Keywords</span></span>|<span data-ttu-id="20ff3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="20ff3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="20ff3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="20ff3-108">Level</span></span>|<span data-ttu-id="20ff3-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="20ff3-109">Warning</span></span>|  
|<span data-ttu-id="20ff3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="20ff3-110">Channel</span></span>|<span data-ttu-id="20ff3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="20ff3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="20ff3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="20ff3-112">Description</span></span>  
 <span data-ttu-id="20ff3-113">Указывает, что было перехвачено исключение SQL.</span><span class="sxs-lookup"><span data-stu-id="20ff3-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="20ff3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="20ff3-114">Message</span></span>  
 <span data-ttu-id="20ff3-115">Обнаружено исключение SQL с номером %1, сообщение %2.</span><span class="sxs-lookup"><span data-stu-id="20ff3-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="20ff3-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="20ff3-116">Details</span></span>  
  
|<span data-ttu-id="20ff3-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="20ff3-117">Data Item Name</span></span>|<span data-ttu-id="20ff3-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="20ff3-118">Data Item Type</span></span>|<span data-ttu-id="20ff3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="20ff3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="20ff3-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="20ff3-120">ErrorNumber</span></span>|<span data-ttu-id="20ff3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ff3-121">xs:string</span></span>|<span data-ttu-id="20ff3-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="20ff3-122">The SQL error number.</span></span>|  
|<span data-ttu-id="20ff3-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="20ff3-123">ExceptionMessage</span></span>|<span data-ttu-id="20ff3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ff3-124">xs:string</span></span>|<span data-ttu-id="20ff3-125">Текст сообщения из исключения SQL.</span><span class="sxs-lookup"><span data-stu-id="20ff3-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="20ff3-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="20ff3-126">AppDomain</span></span>|<span data-ttu-id="20ff3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="20ff3-127">xs:string</span></span>|<span data-ttu-id="20ff3-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="20ff3-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
