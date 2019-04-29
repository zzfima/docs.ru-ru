---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956550"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="12286-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="12286-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="12286-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="12286-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12286-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12286-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="12286-105">Методы</span><span class="sxs-lookup"><span data-stu-id="12286-105">Methods</span></span>  
 <span data-ttu-id="12286-106">Класс TcpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="12286-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="12286-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="12286-107">Properties</span></span>  
 <span data-ttu-id="12286-108">Класс TcpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="12286-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="12286-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="12286-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="12286-110">Тип данных: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="12286-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="12286-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="12286-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12286-112">Настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="12286-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="12286-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="12286-113">ListenBacklog</span></span>  
 <span data-ttu-id="12286-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="12286-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="12286-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="12286-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12286-116">Максимально допустимое количество ожидающих запросов на подключение в очереди.</span><span class="sxs-lookup"><span data-stu-id="12286-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="12286-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="12286-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="12286-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="12286-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="12286-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="12286-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12286-120">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="12286-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="12286-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="12286-121">TeredoEnabled</span></span>  
 <span data-ttu-id="12286-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="12286-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="12286-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="12286-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12286-124">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="12286-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12286-125">Требования</span><span class="sxs-lookup"><span data-stu-id="12286-125">Requirements</span></span>  
  
|<span data-ttu-id="12286-126">MOF</span><span class="sxs-lookup"><span data-stu-id="12286-126">MOF</span></span>|<span data-ttu-id="12286-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="12286-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="12286-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="12286-128">Namespace</span></span>|<span data-ttu-id="12286-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="12286-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12286-130">См. также</span><span class="sxs-lookup"><span data-stu-id="12286-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
