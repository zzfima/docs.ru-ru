---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 58bf07b0429ca2435b5aae3683ef69951a10003e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185187"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="ca16e-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca16e-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="ca16e-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca16e-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca16e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca16e-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ca16e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ca16e-105">Methods</span></span>  
 <span data-ttu-id="ca16e-106">Класс PeerTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="ca16e-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ca16e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="ca16e-107">Properties</span></span>  
 <span data-ttu-id="ca16e-108">Класс PeerTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="ca16e-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="ca16e-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="ca16e-109">ListenIPAddress</span></span>  
 <span data-ttu-id="ca16e-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="ca16e-110">Data type: string</span></span>  
  
 <span data-ttu-id="ca16e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ca16e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca16e-112">IP-адрес, на котором одноранговый узел будет ожидать сообщения.</span><span class="sxs-lookup"><span data-stu-id="ca16e-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="ca16e-113">Порт</span><span class="sxs-lookup"><span data-stu-id="ca16e-113">Port</span></span>  
 <span data-ttu-id="ca16e-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ca16e-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ca16e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ca16e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca16e-116">Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="ca16e-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="ca16e-117">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ca16e-117">Security</span></span>  
 <span data-ttu-id="ca16e-118">Тип данных: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ca16e-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="ca16e-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ca16e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca16e-120">Параметры безопасности однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="ca16e-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca16e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ca16e-121">Requirements</span></span>  
  
|<span data-ttu-id="ca16e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ca16e-122">MOF</span></span>|<span data-ttu-id="ca16e-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ca16e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ca16e-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ca16e-124">Namespace</span></span>|<span data-ttu-id="ca16e-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ca16e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca16e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ca16e-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
