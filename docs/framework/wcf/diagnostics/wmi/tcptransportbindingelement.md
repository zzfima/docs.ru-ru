---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="c671b-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c671b-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="c671b-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c671b-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c671b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c671b-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c671b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c671b-105">Methods</span></span>  
 <span data-ttu-id="c671b-106">Класс TcpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="c671b-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c671b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c671b-107">Properties</span></span>  
 <span data-ttu-id="c671b-108">Класс TcpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c671b-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="c671b-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c671b-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="c671b-110">Тип данных: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c671b-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="c671b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c671b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c671b-112">Настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="c671b-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="c671b-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="c671b-113">ListenBacklog</span></span>  
 <span data-ttu-id="c671b-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="c671b-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c671b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c671b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c671b-116">Максимально допустимое количество ожидающих запросов на подключение в очереди.</span><span class="sxs-lookup"><span data-stu-id="c671b-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="c671b-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="c671b-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="c671b-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c671b-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="c671b-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c671b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c671b-120">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="c671b-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="c671b-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="c671b-121">TeredoEnabled</span></span>  
 <span data-ttu-id="c671b-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="c671b-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="c671b-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c671b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c671b-124">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="c671b-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c671b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="c671b-125">Requirements</span></span>  
  
|<span data-ttu-id="c671b-126">MOF</span><span class="sxs-lookup"><span data-stu-id="c671b-126">MOF</span></span>|<span data-ttu-id="c671b-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c671b-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c671b-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c671b-128">Namespace</span></span>|<span data-ttu-id="c671b-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c671b-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c671b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c671b-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
