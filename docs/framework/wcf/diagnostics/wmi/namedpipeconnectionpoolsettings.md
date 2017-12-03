---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18740c4c87aaeafcd0a28991376e0c45fe688223
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="b6981-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b6981-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="b6981-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b6981-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6981-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6981-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b6981-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b6981-105">Methods</span></span>  
 <span data-ttu-id="b6981-106">Класс NamedPipeConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b6981-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b6981-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b6981-107">Properties</span></span>  
 <span data-ttu-id="b6981-108">Класс NamedPipeConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b6981-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="b6981-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="b6981-109">GroupName</span></span>  
 <span data-ttu-id="b6981-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b6981-110">Data type: string</span></span>  
  
 <span data-ttu-id="b6981-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b6981-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6981-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="b6981-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="b6981-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="b6981-113">IdleTimeout</span></span>  
 <span data-ttu-id="b6981-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="b6981-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="b6981-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b6981-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6981-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="b6981-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="b6981-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b6981-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="b6981-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="b6981-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b6981-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b6981-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b6981-120">Максимальное число исходящих соединений для каждой конечной точки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="b6981-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6981-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b6981-121">Requirements</span></span>  
  
|<span data-ttu-id="b6981-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b6981-122">MOF</span></span>|<span data-ttu-id="b6981-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b6981-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b6981-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b6981-124">Namespace</span></span>|<span data-ttu-id="b6981-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b6981-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6981-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b6981-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
