---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962967"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="0ef50-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0ef50-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="0ef50-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0ef50-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ef50-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0ef50-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0ef50-105">Methods</span></span>  
 <span data-ttu-id="0ef50-106">Класс PeerTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="0ef50-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0ef50-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="0ef50-107">Properties</span></span>  
 <span data-ttu-id="0ef50-108">Класс PeerTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0ef50-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="0ef50-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="0ef50-109">ListenIPAddress</span></span>  
 <span data-ttu-id="0ef50-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0ef50-110">Data type: string</span></span>  
  
 <span data-ttu-id="0ef50-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0ef50-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0ef50-112">IP-адрес, на котором одноранговый узел будет ожидать сообщения.</span><span class="sxs-lookup"><span data-stu-id="0ef50-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="0ef50-113">Порт</span><span class="sxs-lookup"><span data-stu-id="0ef50-113">Port</span></span>  
 <span data-ttu-id="0ef50-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="0ef50-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="0ef50-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0ef50-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0ef50-116">Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="0ef50-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="0ef50-117">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0ef50-117">Security</span></span>  
 <span data-ttu-id="0ef50-118">Тип данных: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="0ef50-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="0ef50-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="0ef50-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0ef50-120">Параметры безопасности однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="0ef50-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef50-121">Требования</span><span class="sxs-lookup"><span data-stu-id="0ef50-121">Requirements</span></span>  
  
|<span data-ttu-id="0ef50-122">MOF</span><span class="sxs-lookup"><span data-stu-id="0ef50-122">MOF</span></span>|<span data-ttu-id="0ef50-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0ef50-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0ef50-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0ef50-124">Namespace</span></span>|<span data-ttu-id="0ef50-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0ef50-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ef50-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0ef50-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
