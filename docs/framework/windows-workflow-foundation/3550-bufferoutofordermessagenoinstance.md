---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="80edb-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="80edb-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="80edb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="80edb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80edb-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="80edb-104">ID</span></span>|<span data-ttu-id="80edb-105">3550</span><span class="sxs-lookup"><span data-stu-id="80edb-105">3550</span></span>|  
|<span data-ttu-id="80edb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="80edb-106">Keywords</span></span>|<span data-ttu-id="80edb-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="80edb-107">WFServices</span></span>|  
|<span data-ttu-id="80edb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="80edb-108">Level</span></span>|<span data-ttu-id="80edb-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="80edb-109">Information</span></span>|  
|<span data-ttu-id="80edb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="80edb-110">Channel</span></span>|<span data-ttu-id="80edb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="80edb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="80edb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="80edb-112">Description</span></span>  
 <span data-ttu-id="80edb-113">Указывает, что получение через буфер не удалось.</span><span class="sxs-lookup"><span data-stu-id="80edb-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="80edb-114">Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="80edb-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="80edb-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="80edb-115">Message</span></span>  
 <span data-ttu-id="80edb-116">Операция «%1» сейчас не может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="80edb-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="80edb-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="80edb-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="80edb-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="80edb-118">Details</span></span>  
  
|<span data-ttu-id="80edb-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="80edb-119">Data Item Name</span></span>|<span data-ttu-id="80edb-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="80edb-120">Data Item Type</span></span>|<span data-ttu-id="80edb-121">Описание</span><span class="sxs-lookup"><span data-stu-id="80edb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="80edb-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="80edb-122">OperationName</span></span>|<span data-ttu-id="80edb-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="80edb-123">xs:string</span></span>|<span data-ttu-id="80edb-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="80edb-124">The name of the operation.</span></span>|  
|<span data-ttu-id="80edb-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="80edb-125">AppDomain</span></span>|<span data-ttu-id="80edb-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="80edb-126">xs:string</span></span>|<span data-ttu-id="80edb-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="80edb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
