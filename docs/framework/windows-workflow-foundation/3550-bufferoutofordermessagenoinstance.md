---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755588"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="fc490-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="fc490-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="fc490-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fc490-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc490-104">ID</span><span class="sxs-lookup"><span data-stu-id="fc490-104">ID</span></span>|<span data-ttu-id="fc490-105">3550</span><span class="sxs-lookup"><span data-stu-id="fc490-105">3550</span></span>|  
|<span data-ttu-id="fc490-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="fc490-106">Keywords</span></span>|<span data-ttu-id="fc490-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="fc490-107">WFServices</span></span>|  
|<span data-ttu-id="fc490-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="fc490-108">Level</span></span>|<span data-ttu-id="fc490-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="fc490-109">Information</span></span>|  
|<span data-ttu-id="fc490-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fc490-110">Channel</span></span>|<span data-ttu-id="fc490-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fc490-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fc490-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fc490-112">Description</span></span>  
 <span data-ttu-id="fc490-113">Указывает, что получение через буфер не удалось.</span><span class="sxs-lookup"><span data-stu-id="fc490-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="fc490-114">Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="fc490-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fc490-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fc490-115">Message</span></span>  
 <span data-ttu-id="fc490-116">Операция «%1» сейчас не может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="fc490-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="fc490-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="fc490-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fc490-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fc490-118">Details</span></span>  
  
|<span data-ttu-id="fc490-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="fc490-119">Data Item Name</span></span>|<span data-ttu-id="fc490-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="fc490-120">Data Item Type</span></span>|<span data-ttu-id="fc490-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fc490-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fc490-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="fc490-122">OperationName</span></span>|<span data-ttu-id="fc490-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc490-123">xs:string</span></span>|<span data-ttu-id="fc490-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="fc490-124">The name of the operation.</span></span>|  
|<span data-ttu-id="fc490-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="fc490-125">AppDomain</span></span>|<span data-ttu-id="fc490-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc490-126">xs:string</span></span>|<span data-ttu-id="fc490-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fc490-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
