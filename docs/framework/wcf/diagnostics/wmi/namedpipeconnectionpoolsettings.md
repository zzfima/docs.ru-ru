---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 77d8403947d341ea2efcef98bbf166f94f75f31f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188733"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="adcef-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="adcef-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="adcef-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="adcef-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adcef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adcef-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="adcef-105">Методы</span><span class="sxs-lookup"><span data-stu-id="adcef-105">Methods</span></span>  
 <span data-ttu-id="adcef-106">Класс NamedPipeConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="adcef-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="adcef-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="adcef-107">Properties</span></span>  
 <span data-ttu-id="adcef-108">Класс NamedPipeConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="adcef-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="adcef-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="adcef-109">GroupName</span></span>  
 <span data-ttu-id="adcef-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="adcef-110">Data type: string</span></span>  
  
 <span data-ttu-id="adcef-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="adcef-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adcef-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="adcef-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="adcef-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="adcef-113">IdleTimeout</span></span>  
 <span data-ttu-id="adcef-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="adcef-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="adcef-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="adcef-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adcef-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="adcef-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="adcef-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="adcef-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="adcef-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="adcef-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="adcef-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="adcef-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adcef-120">Максимальное число исходящих соединений для каждой конечной точки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="adcef-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adcef-121">Требования</span><span class="sxs-lookup"><span data-stu-id="adcef-121">Requirements</span></span>  
  
|<span data-ttu-id="adcef-122">MOF</span><span class="sxs-lookup"><span data-stu-id="adcef-122">MOF</span></span>|<span data-ttu-id="adcef-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="adcef-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="adcef-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="adcef-124">Namespace</span></span>|<span data-ttu-id="adcef-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="adcef-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adcef-126">См. также</span><span class="sxs-lookup"><span data-stu-id="adcef-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
