---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 68e6a25e4e3f47c556363e2fd5aa8d3bb9946449
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485649"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="611b8-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="611b8-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="611b8-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="611b8-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="611b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="611b8-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="611b8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="611b8-105">Methods</span></span>  
 <span data-ttu-id="611b8-106">Класс PeerTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="611b8-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="611b8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="611b8-107">Properties</span></span>  
 <span data-ttu-id="611b8-108">Класс PeerTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="611b8-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="611b8-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="611b8-109">ListenIPAddress</span></span>  
 <span data-ttu-id="611b8-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="611b8-110">Data type: string</span></span>  
  
 <span data-ttu-id="611b8-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="611b8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="611b8-112">IP-адрес, на котором одноранговый узел будет ожидать сообщения.</span><span class="sxs-lookup"><span data-stu-id="611b8-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="611b8-113">Порт</span><span class="sxs-lookup"><span data-stu-id="611b8-113">Port</span></span>  
 <span data-ttu-id="611b8-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="611b8-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="611b8-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="611b8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="611b8-116">Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="611b8-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="611b8-117">Безопасность</span><span class="sxs-lookup"><span data-stu-id="611b8-117">Security</span></span>  
 <span data-ttu-id="611b8-118">Тип данных: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="611b8-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="611b8-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="611b8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="611b8-120">Параметры безопасности однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="611b8-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="611b8-121">Требования</span><span class="sxs-lookup"><span data-stu-id="611b8-121">Requirements</span></span>  
  
|<span data-ttu-id="611b8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="611b8-122">MOF</span></span>|<span data-ttu-id="611b8-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="611b8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="611b8-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="611b8-124">Namespace</span></span>|<span data-ttu-id="611b8-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="611b8-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="611b8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="611b8-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
