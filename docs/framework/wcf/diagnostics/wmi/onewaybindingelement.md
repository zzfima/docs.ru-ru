---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a43707f25a9ee1beb1ce7adac36a2c4a55cab6d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="05b06-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="05b06-102">OneWayBindingElement</span></span>
<span data-ttu-id="05b06-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="05b06-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05b06-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05b06-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="05b06-105">Методы</span><span class="sxs-lookup"><span data-stu-id="05b06-105">Methods</span></span>  
 <span data-ttu-id="05b06-106">Класс OneWayBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="05b06-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="05b06-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="05b06-107">Properties</span></span>  
 <span data-ttu-id="05b06-108">Класс OneWayBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="05b06-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="05b06-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="05b06-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="05b06-110">Тип данных: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="05b06-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="05b06-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="05b06-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05b06-112">Параметры пула каналов.</span><span class="sxs-lookup"><span data-stu-id="05b06-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="05b06-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="05b06-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="05b06-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="05b06-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="05b06-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="05b06-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05b06-116">Максимальное число принимаемых каналов.</span><span class="sxs-lookup"><span data-stu-id="05b06-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="05b06-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="05b06-117">PacketRoutable</span></span>  
 <span data-ttu-id="05b06-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="05b06-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="05b06-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="05b06-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="05b06-120">Значение, указывающее, возможна ли маршрутизация пакета.</span><span class="sxs-lookup"><span data-stu-id="05b06-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05b06-121">Требования</span><span class="sxs-lookup"><span data-stu-id="05b06-121">Requirements</span></span>  
  
|<span data-ttu-id="05b06-122">MOF</span><span class="sxs-lookup"><span data-stu-id="05b06-122">MOF</span></span>|<span data-ttu-id="05b06-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="05b06-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="05b06-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="05b06-124">Namespace</span></span>|<span data-ttu-id="05b06-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="05b06-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05b06-126">См. также</span><span class="sxs-lookup"><span data-stu-id="05b06-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
