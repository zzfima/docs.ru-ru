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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf9c39334289cb30d1a01917c0be37da02fcdc5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="b0997-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b0997-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="b0997-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b0997-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0997-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0997-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b0997-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b0997-105">Methods</span></span>  
 <span data-ttu-id="b0997-106">Класс NamedPipeConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b0997-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0997-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b0997-107">Properties</span></span>  
 <span data-ttu-id="b0997-108">Класс NamedPipeConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b0997-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="b0997-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="b0997-109">GroupName</span></span>  
 <span data-ttu-id="b0997-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b0997-110">Data type: string</span></span>  
  
 <span data-ttu-id="b0997-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b0997-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0997-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="b0997-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="b0997-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="b0997-113">IdleTimeout</span></span>  
 <span data-ttu-id="b0997-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="b0997-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="b0997-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b0997-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0997-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="b0997-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="b0997-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b0997-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="b0997-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="b0997-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0997-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b0997-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0997-120">Максимальное число исходящих соединений для каждой конечной точки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="b0997-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0997-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b0997-121">Requirements</span></span>  
  
|<span data-ttu-id="b0997-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b0997-122">MOF</span></span>|<span data-ttu-id="b0997-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b0997-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0997-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b0997-124">Namespace</span></span>|<span data-ttu-id="b0997-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b0997-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0997-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b0997-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
