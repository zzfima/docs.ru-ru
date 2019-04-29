---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 706cec5c414197ebabda7939728b95be32582e0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963310"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="ef1c6-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ef1c6-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="ef1c6-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ef1c6-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef1c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef1c6-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ef1c6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ef1c6-105">Methods</span></span>  
 <span data-ttu-id="ef1c6-106">Класс MsmqTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ef1c6-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="ef1c6-107">Properties</span></span>  
 <span data-ttu-id="ef1c6-108">Класс MsmqTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="ef1c6-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="ef1c6-109">MaxPoolSize</span></span>  
 <span data-ttu-id="ef1c6-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="ef1c6-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="ef1c6-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ef1c6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef1c6-112">Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="ef1c6-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="ef1c6-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="ef1c6-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="ef1c6-114">Data type: string</span></span>  
  
 <span data-ttu-id="ef1c6-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ef1c6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef1c6-116">Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="ef1c6-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="ef1c6-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="ef1c6-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="ef1c6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef1c6-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="ef1c6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef1c6-120">Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef1c6-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ef1c6-121">Requirements</span></span>  
  
|<span data-ttu-id="ef1c6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ef1c6-122">MOF</span></span>|<span data-ttu-id="ef1c6-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ef1c6-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ef1c6-124">Namespace</span></span>|<span data-ttu-id="ef1c6-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ef1c6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef1c6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ef1c6-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
