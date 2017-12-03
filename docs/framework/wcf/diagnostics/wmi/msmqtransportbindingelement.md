---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 572a19723583a6bc717a71b3b46040148f29e1cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="e655b-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e655b-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="e655b-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e655b-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e655b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e655b-104">Syntax</span></span>  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e655b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e655b-105">Methods</span></span>  
 <span data-ttu-id="e655b-106">Класс MsmqTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="e655b-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e655b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e655b-107">Properties</span></span>  
 <span data-ttu-id="e655b-108">Класс MsmqTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="e655b-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="e655b-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="e655b-109">MaxPoolSize</span></span>  
 <span data-ttu-id="e655b-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="e655b-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="e655b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e655b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e655b-112">Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e655b-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="e655b-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="e655b-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="e655b-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="e655b-114">Data type: string</span></span>  
  
 <span data-ttu-id="e655b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e655b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e655b-116">Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="e655b-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="e655b-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="e655b-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="e655b-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="e655b-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="e655b-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e655b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e655b-120">Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e655b-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e655b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e655b-121">Requirements</span></span>  
  
|<span data-ttu-id="e655b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e655b-122">MOF</span></span>|<span data-ttu-id="e655b-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e655b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e655b-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e655b-124">Namespace</span></span>|<span data-ttu-id="e655b-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e655b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e655b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e655b-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
