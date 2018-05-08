---
title: WCF и WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-and-websockets"></a>WCF и WebSockets
В .NET Framework версии 4.5 добавлена поддержка WebSockets в службах Windows Communication Foundation.  WebSockets - это эффективная, основанная на стандартах технология, обеспечивающая двусторонний обмен сообщениями через стандартные HTTP-порты 80 и 443. Использование стандартных HTTP-портов позволяет WebSockets устанавливать связь по сети через посредников.  Были добавлены две стандартные привязки для поддержки обмена данными через транспорт WebSocket. <xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>. Специальные параметры WebSockets можно настроить на <xref:System.ServiceModel.Channels.HttpTransportBindingElement> , обратившись к <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> свойство.
  
## <a name="in-this-section"></a>В этом разделе  
 [Использование NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Описывает <xref:System.ServiceModel.NetHttpBinding> и его настройку.  
  
 [Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Описывает процесс создания службы WCF, обменивающейся данными через Websockets.  
  
## <a name="reference"></a>Ссылка  
  
## <a name="related-sections"></a>Связанные разделы
