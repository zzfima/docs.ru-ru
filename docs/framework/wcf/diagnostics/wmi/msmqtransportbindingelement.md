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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c0c2c5d54050216c91a318a407341c4ffb9cb687
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="35954-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="35954-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="35954-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="35954-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35954-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35954-104">Syntax</span></span>  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="35954-105">Методы</span><span class="sxs-lookup"><span data-stu-id="35954-105">Methods</span></span>  
 <span data-ttu-id="35954-106">Класс MsmqTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="35954-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="35954-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="35954-107">Properties</span></span>  
 <span data-ttu-id="35954-108">Класс MsmqTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="35954-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="35954-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="35954-109">MaxPoolSize</span></span>  
 <span data-ttu-id="35954-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="35954-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="35954-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="35954-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35954-112">Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="35954-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="35954-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="35954-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="35954-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="35954-114">Data type: string</span></span>  
  
 <span data-ttu-id="35954-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="35954-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35954-116">Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="35954-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="35954-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="35954-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="35954-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="35954-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="35954-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="35954-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="35954-120">Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.</span><span class="sxs-lookup"><span data-stu-id="35954-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35954-121">Требования</span><span class="sxs-lookup"><span data-stu-id="35954-121">Requirements</span></span>  
  
|<span data-ttu-id="35954-122">MOF</span><span class="sxs-lookup"><span data-stu-id="35954-122">MOF</span></span>|<span data-ttu-id="35954-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="35954-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="35954-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="35954-124">Namespace</span></span>|<span data-ttu-id="35954-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="35954-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35954-126">См. также</span><span class="sxs-lookup"><span data-stu-id="35954-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
