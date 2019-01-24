---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 0d5dc5c9b9bf2313d18c9fadb1a2adb87c1b11b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610790"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="1cbf3-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1cbf3-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="1cbf3-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1cbf3-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cbf3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cbf3-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1cbf3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1cbf3-105">Methods</span></span>  
 <span data-ttu-id="1cbf3-106">Класс TcpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1cbf3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1cbf3-107">Properties</span></span>  
 <span data-ttu-id="1cbf3-108">Класс TcpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="1cbf3-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1cbf3-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="1cbf3-110">Тип данных: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1cbf3-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="1cbf3-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1cbf3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1cbf3-112">Настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="1cbf3-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="1cbf3-113">ListenBacklog</span></span>  
 <span data-ttu-id="1cbf3-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="1cbf3-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="1cbf3-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1cbf3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1cbf3-116">Максимально допустимое количество ожидающих запросов на подключение в очереди.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="1cbf3-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="1cbf3-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="1cbf3-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="1cbf3-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="1cbf3-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1cbf3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1cbf3-120">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="1cbf3-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="1cbf3-121">TeredoEnabled</span></span>  
 <span data-ttu-id="1cbf3-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="1cbf3-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="1cbf3-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1cbf3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1cbf3-124">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="1cbf3-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cbf3-125">Требования</span><span class="sxs-lookup"><span data-stu-id="1cbf3-125">Requirements</span></span>  
  
|<span data-ttu-id="1cbf3-126">MOF</span><span class="sxs-lookup"><span data-stu-id="1cbf3-126">MOF</span></span>|<span data-ttu-id="1cbf3-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1cbf3-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1cbf3-128">Namespace</span></span>|<span data-ttu-id="1cbf3-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1cbf3-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cbf3-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1cbf3-130">See also</span></span>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
