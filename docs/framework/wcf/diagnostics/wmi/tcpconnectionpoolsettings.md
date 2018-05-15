---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 4a30ad3ddfef5d39942345b0e0d5274eeff8e596
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="3af2e-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3af2e-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="3af2e-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3af2e-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3af2e-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3af2e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3af2e-105">Methods</span></span>  
 <span data-ttu-id="3af2e-106">Класс TcpConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="3af2e-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3af2e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="3af2e-107">Properties</span></span>  
 <span data-ttu-id="3af2e-108">Класс TcpConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="3af2e-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="3af2e-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="3af2e-109">GroupName</span></span>  
 <span data-ttu-id="3af2e-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="3af2e-110">Data type: string</span></span>  
  
 <span data-ttu-id="3af2e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3af2e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3af2e-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="3af2e-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="3af2e-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="3af2e-113">IdleTimeout</span></span>  
 <span data-ttu-id="3af2e-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="3af2e-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="3af2e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3af2e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3af2e-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="3af2e-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="3af2e-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="3af2e-117">LeaseTimeout</span></span>  
 <span data-ttu-id="3af2e-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="3af2e-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="3af2e-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3af2e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3af2e-120">Максимальное время ожидания завершения выполнения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="3af2e-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="3af2e-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="3af2e-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="3af2e-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3af2e-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="3af2e-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3af2e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3af2e-124">Максимальное число исходящих подключений для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3af2e-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3af2e-125">Требования</span><span class="sxs-lookup"><span data-stu-id="3af2e-125">Requirements</span></span>  
  
|<span data-ttu-id="3af2e-126">MOF</span><span class="sxs-lookup"><span data-stu-id="3af2e-126">MOF</span></span>|<span data-ttu-id="3af2e-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3af2e-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3af2e-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="3af2e-128">Namespace</span></span>|<span data-ttu-id="3af2e-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="3af2e-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3af2e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3af2e-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
