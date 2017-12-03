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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abaacfb6541d41019a8d0cd6df53913c6b7911f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс OneWayBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс OneWayBindingElement имеет следующие свойства.  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 Тип данных: ChannelPoolSettings  
  
 Тип доступа: только для чтения  
  
 Параметры пула каналов.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число принимаемых каналов.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, возможна ли маршрутизация пакета.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
