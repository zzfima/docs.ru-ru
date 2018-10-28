---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 34220a3651819978f5f597fdc67d54630ec5e059
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195818"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="7ae7f-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="7ae7f-102">OneWayBindingElement</span></span>
<span data-ttu-id="7ae7f-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="7ae7f-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ae7f-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7ae7f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7ae7f-105">Methods</span></span>  
 <span data-ttu-id="7ae7f-106">Класс OneWayBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7ae7f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="7ae7f-107">Properties</span></span>  
 <span data-ttu-id="7ae7f-108">Класс OneWayBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="7ae7f-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7ae7f-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="7ae7f-110">Тип данных: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="7ae7f-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="7ae7f-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7ae7f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae7f-112">Параметры пула каналов.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="7ae7f-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="7ae7f-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="7ae7f-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="7ae7f-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="7ae7f-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7ae7f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae7f-116">Максимальное число принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="7ae7f-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="7ae7f-117">PacketRoutable</span></span>  
 <span data-ttu-id="7ae7f-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="7ae7f-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="7ae7f-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7ae7f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7ae7f-120">Значение, указывающее, возможна ли маршрутизация пакета.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae7f-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7ae7f-121">Requirements</span></span>  
  
|<span data-ttu-id="7ae7f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7ae7f-122">MOF</span></span>|<span data-ttu-id="7ae7f-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7ae7f-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7ae7f-124">Namespace</span></span>|<span data-ttu-id="7ae7f-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ae7f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae7f-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
