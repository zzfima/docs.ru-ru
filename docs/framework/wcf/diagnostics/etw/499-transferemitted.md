---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33469512"
---
# <a name="499---transferemitted"></a><span data-ttu-id="3c0dc-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="3c0dc-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="3c0dc-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3c0dc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c0dc-104">ID</span><span class="sxs-lookup"><span data-stu-id="3c0dc-104">ID</span></span>|<span data-ttu-id="3c0dc-105">499</span><span class="sxs-lookup"><span data-stu-id="3c0dc-105">499</span></span>|  
|<span data-ttu-id="3c0dc-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3c0dc-106">Keywords</span></span>|<span data-ttu-id="3c0dc-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="3c0dc-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="3c0dc-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3c0dc-108">Level</span></span>|<span data-ttu-id="3c0dc-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="3c0dc-109">LogAlways</span></span>|  
|<span data-ttu-id="3c0dc-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3c0dc-110">Channel</span></span>|<span data-ttu-id="3c0dc-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3c0dc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c0dc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3c0dc-112">Description</span></span>  
 <span data-ttu-id="3c0dc-113">Это событие формируется при возникновении события передачи.</span><span class="sxs-lookup"><span data-stu-id="3c0dc-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c0dc-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3c0dc-114">Message</span></span>  
 <span data-ttu-id="3c0dc-115">Произошло событие передачи.</span><span class="sxs-lookup"><span data-stu-id="3c0dc-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c0dc-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3c0dc-116">Details</span></span>  
  
|<span data-ttu-id="3c0dc-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3c0dc-117">Data Item Name</span></span>|<span data-ttu-id="3c0dc-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3c0dc-118">Data Item Type</span></span>|<span data-ttu-id="3c0dc-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3c0dc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c0dc-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="3c0dc-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="3c0dc-121">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="3c0dc-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3c0dc-122">Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы".</span><span class="sxs-lookup"><span data-stu-id="3c0dc-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3c0dc-123">Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="3c0dc-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3c0dc-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3c0dc-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3c0dc-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3c0dc-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
