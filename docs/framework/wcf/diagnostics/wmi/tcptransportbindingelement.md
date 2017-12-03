---
title: TcpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b9aa7e0d9eaba0181b17b44da1bf871c10af814
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="9de73-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9de73-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="9de73-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9de73-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de73-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9de73-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9de73-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9de73-105">Methods</span></span>  
 <span data-ttu-id="9de73-106">Класс TcpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="9de73-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9de73-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="9de73-107">Properties</span></span>  
 <span data-ttu-id="9de73-108">Класс TcpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9de73-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="9de73-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9de73-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="9de73-110">Тип данных: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9de73-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="9de73-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="9de73-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9de73-112">Настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="9de73-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="9de73-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="9de73-113">ListenBacklog</span></span>  
 <span data-ttu-id="9de73-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="9de73-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9de73-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="9de73-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9de73-116">Максимально допустимое количество ожидающих запросов на подключение в очереди.</span><span class="sxs-lookup"><span data-stu-id="9de73-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="9de73-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="9de73-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="9de73-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="9de73-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="9de73-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="9de73-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9de73-120">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="9de73-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="9de73-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="9de73-121">TeredoEnabled</span></span>  
 <span data-ttu-id="9de73-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="9de73-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="9de73-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="9de73-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9de73-124">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="9de73-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9de73-125">Требования</span><span class="sxs-lookup"><span data-stu-id="9de73-125">Requirements</span></span>  
  
|<span data-ttu-id="9de73-126">MOF</span><span class="sxs-lookup"><span data-stu-id="9de73-126">MOF</span></span>|<span data-ttu-id="9de73-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9de73-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9de73-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9de73-128">Namespace</span></span>|<span data-ttu-id="9de73-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="9de73-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9de73-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9de73-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
