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
ms.workload: dotnet
ms.openlocfilehash: 541770db6b9cc624fd08ab4db275bc63fa5deca9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="29ad7-102">Расширяемость каналов</span><span class="sxs-lookup"><span data-stu-id="29ad7-102">Channels Extensibility</span></span>
<span data-ttu-id="29ad7-103">В этом разделе содержатся образцы, демонстрирующие пользовательские каналы.</span><span class="sxs-lookup"><span data-stu-id="29ad7-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29ad7-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="29ad7-104">In This Section</span></span>  
 [<span data-ttu-id="29ad7-105">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="29ad7-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="29ad7-106">Демонстрирует локальный канал транспорта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который используется для связи внутри одного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="29ad7-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="29ad7-107">Надежный защищенный профиль</span><span class="sxs-lookup"><span data-stu-id="29ad7-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="29ad7-108">Показано использование [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместе с надежным защищенным профилем (RSP).</span><span class="sxs-lookup"><span data-stu-id="29ad7-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="29ad7-109">Настраиваемый диспетчер каналов</span><span class="sxs-lookup"><span data-stu-id="29ad7-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="29ad7-110">Демонстрирует построение пользовательского стека каналов путем непосредственной реализации <xref:System.ServiceModel.ServiceHostBase>, а также создание пользовательского диспетчера каналов в среде веб-узла.</span><span class="sxs-lookup"><span data-stu-id="29ad7-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="29ad7-111">Фрагментирование канала</span><span class="sxs-lookup"><span data-stu-id="29ad7-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="29ad7-112">Показывает способы ограничения объема памяти, используемого для буферизации больших сообщений, отправляемых с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29ad7-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="29ad7-113">Канал подтверждений HTTP</span><span class="sxs-lookup"><span data-stu-id="29ad7-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="29ad7-114">Демонстрирует многоуровневый канал, изменяющий односторонний шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="29ad7-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="29ad7-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="29ad7-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="29ad7-116">Демонстрирует, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="29ad7-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="29ad7-117">Пользовательский перехватчик сообщений</span><span class="sxs-lookup"><span data-stu-id="29ad7-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="29ad7-118">Показано, как реализовать пользовательский элемент привязки, который создает фабрики и прослушиватели каналов для перехвата всех входящих и исходящих сообщений в определенной точке стека времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="29ad7-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
