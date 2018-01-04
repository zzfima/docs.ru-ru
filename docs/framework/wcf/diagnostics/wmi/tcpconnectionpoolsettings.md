---
title: TcpConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04e6a457a9f4c3f93a52f851aafe70578b7d7444
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="0d5d7-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0d5d7-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="0d5d7-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0d5d7-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d5d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d5d7-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0d5d7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0d5d7-105">Methods</span></span>  
 <span data-ttu-id="0d5d7-106">Класс TcpConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0d5d7-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="0d5d7-107">Properties</span></span>  
 <span data-ttu-id="0d5d7-108">Класс TcpConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="0d5d7-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="0d5d7-109">GroupName</span></span>  
 <span data-ttu-id="0d5d7-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0d5d7-110">Data type: string</span></span>  
  
 <span data-ttu-id="0d5d7-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0d5d7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d5d7-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="0d5d7-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="0d5d7-113">IdleTimeout</span></span>  
 <span data-ttu-id="0d5d7-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="0d5d7-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="0d5d7-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0d5d7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d5d7-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="0d5d7-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="0d5d7-117">LeaseTimeout</span></span>  
 <span data-ttu-id="0d5d7-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="0d5d7-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="0d5d7-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0d5d7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d5d7-120">Максимальное время ожидания завершения выполнения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="0d5d7-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0d5d7-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="0d5d7-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="0d5d7-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="0d5d7-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0d5d7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0d5d7-124">Максимальное число исходящих подключений для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d5d7-125">Требования</span><span class="sxs-lookup"><span data-stu-id="0d5d7-125">Requirements</span></span>  
  
|<span data-ttu-id="0d5d7-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0d5d7-126">MOF</span></span>|<span data-ttu-id="0d5d7-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0d5d7-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0d5d7-128">Namespace</span></span>|<span data-ttu-id="0d5d7-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0d5d7-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d5d7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0d5d7-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
