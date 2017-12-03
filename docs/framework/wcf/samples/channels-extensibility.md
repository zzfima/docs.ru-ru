---
title: "Расширяемость каналов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcda7f9edc741e8f0c9c56214119255ca2777d77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="920fc-102">Расширяемость каналов</span><span class="sxs-lookup"><span data-stu-id="920fc-102">Channels Extensibility</span></span>
<span data-ttu-id="920fc-103">В этом разделе содержатся образцы, демонстрирующие пользовательские каналы.</span><span class="sxs-lookup"><span data-stu-id="920fc-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="920fc-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="920fc-104">In This Section</span></span>  
 [<span data-ttu-id="920fc-105">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="920fc-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="920fc-106">Демонстрирует локальный канал транспорта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который используется для связи внутри одного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="920fc-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="920fc-107">Надежный защищенный профиль</span><span class="sxs-lookup"><span data-stu-id="920fc-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="920fc-108">Показано использование [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместе с надежным защищенным профилем (RSP).</span><span class="sxs-lookup"><span data-stu-id="920fc-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="920fc-109">Настраиваемый диспетчер каналов</span><span class="sxs-lookup"><span data-stu-id="920fc-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="920fc-110">Демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла.</span><span class="sxs-lookup"><span data-stu-id="920fc-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="920fc-111">Фрагментирование канала</span><span class="sxs-lookup"><span data-stu-id="920fc-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="920fc-112">Показывает способы ограничения объема памяти, используемого для буферизации больших сообщений, отправляемых с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="920fc-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="920fc-113">Канал подтверждения HTTP</span><span class="sxs-lookup"><span data-stu-id="920fc-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="920fc-114">Демонстрирует многоуровневый канал, изменяющий односторонний шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="920fc-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="920fc-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="920fc-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="920fc-116">Демонстрирует, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="920fc-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="920fc-117">Пользовательский перехватчик сообщений</span><span class="sxs-lookup"><span data-stu-id="920fc-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="920fc-118">Показано, как реализовать пользовательский элемент привязки, который создает фабрики и прослушиватели каналов для перехвата всех входящих и исходящих сообщений в определенной точке стека времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="920fc-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
