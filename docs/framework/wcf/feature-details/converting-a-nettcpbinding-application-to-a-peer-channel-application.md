---
title: Преобразование приложения NetTcpBinding в приложение одноранговых каналов
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 362945959a781fac360c42475148fee1e47a1183
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960133"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="79169-102">Преобразование приложения NetTcpBinding в приложение одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="79169-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="79169-103">Можно создавать подключения между клиентами, с помощью WinFX с помощью привязки, описывающие параметры подключения.</span><span class="sxs-lookup"><span data-stu-id="79169-103">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="79169-104">Преобразование приложения .NET Framework для использования подключений peer-to-peer требуется привязка, поддерживающая эту технологию при установлении соединений клиента.</span><span class="sxs-lookup"><span data-stu-id="79169-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="79169-105">Одноранговый канал предоставляет привязку, называемую <xref:System.ServiceModel.NetPeerTcpBinding>, которую можно использовать аналогично привязке <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="79169-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="79169-106">Основное отличие в том, как задается служба распознавателя и определяются параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="79169-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="79169-107">Если приложение использует распознаватель и параметры безопасности по умолчанию, преобразование обычного клиентско-серверного приложения для использования однорангового канала предполагает изменение имени привязки с "NetTcpBinding" на "NetPeerTcpBinding" в файле конфигурации приложения, при этом не требуется изменять базу кода приложения.</span><span class="sxs-lookup"><span data-stu-id="79169-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79169-108">См. также</span><span class="sxs-lookup"><span data-stu-id="79169-108">See also</span></span>

- [<span data-ttu-id="79169-109">Создание приложения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="79169-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [<span data-ttu-id="79169-110">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="79169-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
