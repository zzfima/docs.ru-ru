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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5038d093333eca9ca191c3ecae4cfa889d723276
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="d29b8-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d29b8-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="d29b8-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d29b8-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d29b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d29b8-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d29b8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d29b8-105">Methods</span></span>  
 <span data-ttu-id="d29b8-106">Класс TcpConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d29b8-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d29b8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d29b8-107">Properties</span></span>  
 <span data-ttu-id="d29b8-108">Класс TcpConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d29b8-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="d29b8-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="d29b8-109">GroupName</span></span>  
 <span data-ttu-id="d29b8-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d29b8-110">Data type: string</span></span>  
  
 <span data-ttu-id="d29b8-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d29b8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d29b8-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="d29b8-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="d29b8-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="d29b8-113">IdleTimeout</span></span>  
 <span data-ttu-id="d29b8-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="d29b8-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="d29b8-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d29b8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d29b8-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="d29b8-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="d29b8-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="d29b8-117">LeaseTimeout</span></span>  
 <span data-ttu-id="d29b8-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="d29b8-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="d29b8-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d29b8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d29b8-120">Максимальное время ожидания завершения выполнения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="d29b8-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="d29b8-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d29b8-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="d29b8-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="d29b8-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="d29b8-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d29b8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d29b8-124">Максимальное число исходящих подключений для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d29b8-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d29b8-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d29b8-125">Requirements</span></span>  
  
|<span data-ttu-id="d29b8-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d29b8-126">MOF</span></span>|<span data-ttu-id="d29b8-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d29b8-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d29b8-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d29b8-128">Namespace</span></span>|<span data-ttu-id="d29b8-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d29b8-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d29b8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d29b8-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
