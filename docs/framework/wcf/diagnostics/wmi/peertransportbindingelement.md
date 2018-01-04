---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25893b1f3cf6cf20ae674bade5090a70c5f381a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="11139-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="11139-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="11139-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="11139-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11139-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11139-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="11139-105">Методы</span><span class="sxs-lookup"><span data-stu-id="11139-105">Methods</span></span>  
 <span data-ttu-id="11139-106">Класс PeerTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="11139-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="11139-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="11139-107">Properties</span></span>  
 <span data-ttu-id="11139-108">Класс PeerTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="11139-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="11139-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="11139-109">ListenIPAddress</span></span>  
 <span data-ttu-id="11139-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="11139-110">Data type: string</span></span>  
  
 <span data-ttu-id="11139-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="11139-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11139-112">IP-адрес, на котором одноранговый узел будет ожидать сообщения.</span><span class="sxs-lookup"><span data-stu-id="11139-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="11139-113">Порт</span><span class="sxs-lookup"><span data-stu-id="11139-113">Port</span></span>  
 <span data-ttu-id="11139-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="11139-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="11139-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="11139-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11139-116">Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="11139-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="11139-117">Безопасность</span><span class="sxs-lookup"><span data-stu-id="11139-117">Security</span></span>  
 <span data-ttu-id="11139-118">Тип данных: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="11139-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="11139-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="11139-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11139-120">Параметры безопасности однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="11139-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11139-121">Требования</span><span class="sxs-lookup"><span data-stu-id="11139-121">Requirements</span></span>  
  
|<span data-ttu-id="11139-122">MOF</span><span class="sxs-lookup"><span data-stu-id="11139-122">MOF</span></span>|<span data-ttu-id="11139-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="11139-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="11139-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="11139-124">Namespace</span></span>|<span data-ttu-id="11139-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="11139-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11139-126">См. также</span><span class="sxs-lookup"><span data-stu-id="11139-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
