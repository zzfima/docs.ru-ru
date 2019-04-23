---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 6fa68eed241edaea40b66c31240a4201e05779f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975358"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="95388-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="95388-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="95388-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="95388-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95388-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95388-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="95388-105">Методы</span><span class="sxs-lookup"><span data-stu-id="95388-105">Methods</span></span>  
 <span data-ttu-id="95388-106">Класс TcpConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="95388-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="95388-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="95388-107">Properties</span></span>  
 <span data-ttu-id="95388-108">Класс TcpConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="95388-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="95388-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="95388-109">GroupName</span></span>  
 <span data-ttu-id="95388-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="95388-110">Data type: string</span></span>  
  
 <span data-ttu-id="95388-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="95388-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95388-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="95388-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="95388-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="95388-113">IdleTimeout</span></span>  
 <span data-ttu-id="95388-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="95388-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="95388-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="95388-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95388-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="95388-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="95388-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="95388-117">LeaseTimeout</span></span>  
 <span data-ttu-id="95388-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="95388-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="95388-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="95388-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95388-120">Максимальное время ожидания завершения выполнения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="95388-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="95388-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="95388-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="95388-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="95388-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="95388-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="95388-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95388-124">Максимальное число исходящих подключений для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="95388-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95388-125">Требования</span><span class="sxs-lookup"><span data-stu-id="95388-125">Requirements</span></span>  
  
|<span data-ttu-id="95388-126">MOF</span><span class="sxs-lookup"><span data-stu-id="95388-126">MOF</span></span>|<span data-ttu-id="95388-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="95388-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="95388-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="95388-128">Namespace</span></span>|<span data-ttu-id="95388-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="95388-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95388-130">См. также</span><span class="sxs-lookup"><span data-stu-id="95388-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
