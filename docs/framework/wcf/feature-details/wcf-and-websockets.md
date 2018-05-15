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
# <a name="wcf-and-websockets"></a><span data-ttu-id="7e112-102">WCF и WebSockets</span><span class="sxs-lookup"><span data-stu-id="7e112-102">WCF and WebSockets</span></span>
<span data-ttu-id="7e112-103">В .NET Framework версии 4.5 добавлена поддержка WebSockets в службах Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="7e112-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="7e112-104">WebSockets - это эффективная, основанная на стандартах технология, обеспечивающая двусторонний обмен сообщениями через стандартные HTTP-порты 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="7e112-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="7e112-105">Использование стандартных HTTP-портов позволяет WebSockets устанавливать связь по сети через посредников.</span><span class="sxs-lookup"><span data-stu-id="7e112-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="7e112-106">Были добавлены две стандартные привязки для поддержки обмена данными через транспорт WebSocket.</span><span class="sxs-lookup"><span data-stu-id="7e112-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="7e112-107"><xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="7e112-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="7e112-108">Специальные параметры WebSockets можно настроить на <xref:System.ServiceModel.Channels.HttpTransportBindingElement> , обратившись к <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7e112-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7e112-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7e112-109">In This Section</span></span>  
 [<span data-ttu-id="7e112-110">Использование NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="7e112-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="7e112-111">Описывает <xref:System.ServiceModel.NetHttpBinding> и его настройку.</span><span class="sxs-lookup"><span data-stu-id="7e112-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="7e112-112">Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets</span><span class="sxs-lookup"><span data-stu-id="7e112-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="7e112-113">Описывает процесс создания службы WCF, обменивающейся данными через Websockets.</span><span class="sxs-lookup"><span data-stu-id="7e112-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7e112-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="7e112-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7e112-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7e112-115">Related Sections</span></span>
