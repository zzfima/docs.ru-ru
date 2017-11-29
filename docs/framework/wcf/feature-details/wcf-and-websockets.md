---
title: "WCF и WebSockets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 726b23f0dc3f5953611010dca5260cc19c7adaaf
ms.sourcegitcommit: 8d14e8c1b15009330c9880f8523686158924e1a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2017
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="36c9e-102">WCF и WebSockets</span><span class="sxs-lookup"><span data-stu-id="36c9e-102">WCF and WebSockets</span></span>
<span data-ttu-id="36c9e-103">В .NET Framework версии 4.5 добавлена поддержка WebSockets в службах Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="36c9e-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="36c9e-104">WebSockets - это эффективная, основанная на стандартах технология, обеспечивающая двусторонний обмен сообщениями через стандартные HTTP-порты 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="36c9e-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="36c9e-105">Использование стандартных HTTP-портов позволяет WebSockets устанавливать связь по сети через посредников.</span><span class="sxs-lookup"><span data-stu-id="36c9e-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="36c9e-106">Были добавлены две стандартные привязки для поддержки обмена данными через транспорт WebSocket.</span><span class="sxs-lookup"><span data-stu-id="36c9e-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="36c9e-107"><xref:System.ServiceModel.NetHttpBinding> и <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="36c9e-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="36c9e-108">Специальные параметры WebSockets можно настроить на <xref:System.ServiceModel.Channels.HttpTransportBindingElement> , обратившись к <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="36c9e-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="36c9e-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="36c9e-109">In This Section</span></span>  
 [<span data-ttu-id="36c9e-110">Использование NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="36c9e-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="36c9e-111">Описывает <xref:System.ServiceModel.NetHttpBinding> и его настройку.</span><span class="sxs-lookup"><span data-stu-id="36c9e-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="36c9e-112">Как: создание службы WCF, обменивающейся данными через WebSockets</span><span class="sxs-lookup"><span data-stu-id="36c9e-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="36c9e-113">Описывает процесс создания службы WCF, обменивающейся данными через Websockets.</span><span class="sxs-lookup"><span data-stu-id="36c9e-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="36c9e-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="36c9e-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="36c9e-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="36c9e-115">Related Sections</span></span>
