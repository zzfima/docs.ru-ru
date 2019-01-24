---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: d37ee4527226d9347e24fc2ee8007a263c71f198
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564881"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="06c9c-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="06c9c-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="06c9c-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="06c9c-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06c9c-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="06c9c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="06c9c-105">Methods</span></span>  
 <span data-ttu-id="06c9c-106">Класс MsmqTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="06c9c-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="06c9c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="06c9c-107">Properties</span></span>  
 <span data-ttu-id="06c9c-108">Класс MsmqTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="06c9c-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="06c9c-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="06c9c-109">MaxPoolSize</span></span>  
 <span data-ttu-id="06c9c-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="06c9c-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="06c9c-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="06c9c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06c9c-112">Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="06c9c-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="06c9c-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="06c9c-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="06c9c-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="06c9c-114">Data type: string</span></span>  
  
 <span data-ttu-id="06c9c-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="06c9c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06c9c-116">Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="06c9c-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="06c9c-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="06c9c-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="06c9c-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="06c9c-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="06c9c-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="06c9c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06c9c-120">Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06c9c-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06c9c-121">Требования</span><span class="sxs-lookup"><span data-stu-id="06c9c-121">Requirements</span></span>  
  
|<span data-ttu-id="06c9c-122">MOF</span><span class="sxs-lookup"><span data-stu-id="06c9c-122">MOF</span></span>|<span data-ttu-id="06c9c-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="06c9c-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="06c9c-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="06c9c-124">Namespace</span></span>|<span data-ttu-id="06c9c-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="06c9c-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06c9c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="06c9c-126">See also</span></span>
- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
