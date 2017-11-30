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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 180e954661319cb32edfd3180418fe9b1571ea5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="8ce86-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="8ce86-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="8ce86-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="8ce86-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ce86-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8ce86-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8ce86-105">Methods</span></span>  
 <span data-ttu-id="8ce86-106">Класс TcpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="8ce86-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8ce86-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="8ce86-107">Properties</span></span>  
 <span data-ttu-id="8ce86-108">Класс TcpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8ce86-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="8ce86-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8ce86-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="8ce86-110">Тип данных: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8ce86-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="8ce86-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8ce86-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ce86-112">Настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="8ce86-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="8ce86-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="8ce86-113">ListenBacklog</span></span>  
 <span data-ttu-id="8ce86-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8ce86-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="8ce86-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8ce86-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ce86-116">Максимально допустимое количество ожидающих запросов на подключение в очереди.</span><span class="sxs-lookup"><span data-stu-id="8ce86-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="8ce86-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="8ce86-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="8ce86-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8ce86-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="8ce86-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8ce86-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ce86-120">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="8ce86-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="8ce86-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="8ce86-121">TeredoEnabled</span></span>  
 <span data-ttu-id="8ce86-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="8ce86-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="8ce86-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8ce86-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8ce86-124">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="8ce86-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ce86-125">Требования</span><span class="sxs-lookup"><span data-stu-id="8ce86-125">Requirements</span></span>  
  
|<span data-ttu-id="8ce86-126">MOF</span><span class="sxs-lookup"><span data-stu-id="8ce86-126">MOF</span></span>|<span data-ttu-id="8ce86-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8ce86-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8ce86-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8ce86-128">Namespace</span></span>|<span data-ttu-id="8ce86-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8ce86-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ce86-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8ce86-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
