---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755536"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="d9fc1-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="d9fc1-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="d9fc1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d9fc1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9fc1-104">ID</span><span class="sxs-lookup"><span data-stu-id="d9fc1-104">ID</span></span>|<span data-ttu-id="d9fc1-105">3551</span><span class="sxs-lookup"><span data-stu-id="d9fc1-105">3551</span></span>|  
|<span data-ttu-id="d9fc1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d9fc1-106">Keywords</span></span>|<span data-ttu-id="d9fc1-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d9fc1-107">WFServices</span></span>|  
|<span data-ttu-id="d9fc1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d9fc1-108">Level</span></span>|<span data-ttu-id="d9fc1-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d9fc1-109">Information</span></span>|  
|<span data-ttu-id="d9fc1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d9fc1-110">Channel</span></span>|<span data-ttu-id="d9fc1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d9fc1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d9fc1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d9fc1-112">Description</span></span>  
 <span data-ttu-id="d9fc1-113">Указывает на сбой возобновления закладки.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="d9fc1-114">Следующая попытка выполнить операцию получения через буфер будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d9fc1-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d9fc1-115">Message</span></span>  
 <span data-ttu-id="d9fc1-116">Операция «%2» в экземпляре службы «%1» не может быть выполнена в данный момент.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="d9fc1-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9fc1-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d9fc1-118">Details</span></span>  
  
|<span data-ttu-id="d9fc1-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d9fc1-119">Data Item Name</span></span>|<span data-ttu-id="d9fc1-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d9fc1-120">Data Item Type</span></span>|<span data-ttu-id="d9fc1-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d9fc1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d9fc1-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="d9fc1-122">OperationName</span></span>|<span data-ttu-id="d9fc1-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9fc1-123">xs:string</span></span>|<span data-ttu-id="d9fc1-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-124">The name of the operation.</span></span>|  
|<span data-ttu-id="d9fc1-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="d9fc1-125">ServiceInstanceId</span></span>|<span data-ttu-id="d9fc1-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9fc1-126">xs:string</span></span>|<span data-ttu-id="d9fc1-127">Идентификатор экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="d9fc1-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="d9fc1-128">AppDomain</span></span>|<span data-ttu-id="d9fc1-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="d9fc1-129">xs:string</span></span>|<span data-ttu-id="d9fc1-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d9fc1-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
