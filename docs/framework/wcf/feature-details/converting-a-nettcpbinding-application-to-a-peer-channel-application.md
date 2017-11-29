---
title: "Преобразование приложения NetTcpBinding в приложение одноранговых каналов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 532171dfeba965ae30dc92f31448cf38964fc695
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="ed4a5-102">Преобразование приложения NetTcpBinding в приложение одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="ed4a5-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="ed4a5-103">Привязки, описывающие параметры подключения, позволяют создавать подключения между клиентами с использованием [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed4a5-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="ed4a5-104">Преобразование приложения [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для использования одноранговых подключений требует привязки, которая поддерживает эту технологию при установке клиентских подключений.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-104">Converting a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="ed4a5-105">Одноранговый канал предоставляет привязку, называемую <xref:System.ServiceModel.NetPeerTcpBinding>, которую можно использовать аналогично привязке <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="ed4a5-106">Основное отличие в том, как задается служба распознавателя и определяются параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="ed4a5-107">Если приложение использует распознаватель и параметры безопасности по умолчанию, преобразование обычного клиентско-серверного приложения для использования однорангового канала предполагает изменение имени привязки с "NetTcpBinding" на "NetPeerTcpBinding" в файле конфигурации приложения, при этом не требуется изменять базу кода приложения.</span><span class="sxs-lookup"><span data-stu-id="ed4a5-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4a5-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ed4a5-108">See Also</span></span>  
 [<span data-ttu-id="ed4a5-109">Создание приложения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="ed4a5-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 [<span data-ttu-id="ed4a5-110">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="ed4a5-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
