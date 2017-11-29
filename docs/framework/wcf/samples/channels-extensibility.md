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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e0cf92edc4ec05df3e5e8c25b90bcf253e94ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="a0894-102">Расширяемость каналов</span><span class="sxs-lookup"><span data-stu-id="a0894-102">Channels Extensibility</span></span>
<span data-ttu-id="a0894-103">В этом разделе содержатся образцы, демонстрирующие пользовательские каналы.</span><span class="sxs-lookup"><span data-stu-id="a0894-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0894-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="a0894-104">In This Section</span></span>  
 [<span data-ttu-id="a0894-105">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="a0894-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="a0894-106">Демонстрирует локальный канал транспорта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который используется для связи внутри одного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="a0894-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="a0894-107">Надежный защищенный профиль</span><span class="sxs-lookup"><span data-stu-id="a0894-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="a0894-108">Показано использование [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместе с надежным защищенным профилем (RSP).</span><span class="sxs-lookup"><span data-stu-id="a0894-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="a0894-109">Настраиваемый диспетчер каналов</span><span class="sxs-lookup"><span data-stu-id="a0894-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="a0894-110">Демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла.</span><span class="sxs-lookup"><span data-stu-id="a0894-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="a0894-111">Фрагментирование канала</span><span class="sxs-lookup"><span data-stu-id="a0894-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="a0894-112">Показывает способы ограничения объема памяти, используемого для буферизации больших сообщений, отправляемых с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0894-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="a0894-113">Канал подтверждения HTTP</span><span class="sxs-lookup"><span data-stu-id="a0894-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="a0894-114">Демонстрирует многоуровневый канал, изменяющий односторонний шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a0894-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="a0894-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="a0894-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="a0894-116">Демонстрирует, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="a0894-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="a0894-117">Пользовательский перехватчик сообщений</span><span class="sxs-lookup"><span data-stu-id="a0894-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="a0894-118">Показано, как реализовать пользовательский элемент привязки, который создает фабрики и прослушиватели каналов для перехвата всех входящих и исходящих сообщений в определенной точке стека времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0894-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
