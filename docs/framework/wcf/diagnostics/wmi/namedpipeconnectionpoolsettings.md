---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8c2d4bfc08a503a8d6eb0e8abf6f1e798b90bc83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773705"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="f3199-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f3199-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="f3199-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f3199-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3199-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3199-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f3199-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f3199-105">Methods</span></span>  
 <span data-ttu-id="f3199-106">Класс NamedPipeConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f3199-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f3199-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f3199-107">Properties</span></span>  
 <span data-ttu-id="f3199-108">Класс NamedPipeConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f3199-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="f3199-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="f3199-109">GroupName</span></span>  
 <span data-ttu-id="f3199-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f3199-110">Data type: string</span></span>  
  
 <span data-ttu-id="f3199-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f3199-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3199-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="f3199-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="f3199-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f3199-113">IdleTimeout</span></span>  
 <span data-ttu-id="f3199-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="f3199-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="f3199-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f3199-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3199-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="f3199-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="f3199-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f3199-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="f3199-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f3199-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f3199-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="f3199-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f3199-120">Максимальное число исходящих соединений для каждой конечной точки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="f3199-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3199-121">Требования</span><span class="sxs-lookup"><span data-stu-id="f3199-121">Requirements</span></span>  
  
|<span data-ttu-id="f3199-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f3199-122">MOF</span></span>|<span data-ttu-id="f3199-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f3199-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f3199-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f3199-124">Namespace</span></span>|<span data-ttu-id="f3199-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f3199-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3199-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f3199-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
