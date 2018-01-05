---
title: "Транспорты в Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62eb27919e762004667b3d5179c35cb04d9a9422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="2bb9b-102">Транспорты в Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="2bb9b-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="2bb9b-103">Транспортный уровень является самым нижним уровнем стека каналов.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="2bb9b-104">Основными типами транспорта, используемыми в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], являются протоколы HTTP, HTTPS, TCP и именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-104">The main transports used in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="2bb9b-105">В подразделах данного раздела рассматриваются выбор типа транспорта среди названных выше типов, настройка транспорта и задание свойств настройки.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2bb9b-106"> содержит дополнительные типы транспорта.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-106"> includes additional transports.</span></span> <span data-ttu-id="2bb9b-107">Сведения о транспорта очереди сообщений (MSMQ) см. в разделе [очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="2bb9b-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="2bb9b-108">Сведения о транспорта одноранговая сеть, в разделе [-одноранговые сети](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="2bb9b-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bb9b-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2bb9b-109">In This Section</span></span>  
 [<span data-ttu-id="2bb9b-110">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="2bb9b-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="2bb9b-111">Описываются три основных типа транспорта и рассматриваются вопросы выбора транспорта.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="2bb9b-112">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="2bb9b-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="2bb9b-113">Описываются факторы, которые необходимо принять во внимание при выборе элемента привязки для кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="2bb9b-114">Потоковая передача сообщений</span><span class="sxs-lookup"><span data-stu-id="2bb9b-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="2bb9b-115">Описывается настройка транспортного уровня для выполнения потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="2bb9b-116">Настройка HTTP и HTTPS</span><span class="sxs-lookup"><span data-stu-id="2bb9b-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="2bb9b-117">Описывается настройка элементов привязки транспорта HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="2bb9b-118">Практическое руководство. Замена резервирования URL с помощью WCF на ограниченное резервирование</span><span class="sxs-lookup"><span data-stu-id="2bb9b-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="2bb9b-119">Описывает использование ограниченных резервирований URL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bb9b-119">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL restricted reservations.</span></span>  
  
 [<span data-ttu-id="2bb9b-120">Квоты транспорта</span><span class="sxs-lookup"><span data-stu-id="2bb9b-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="2bb9b-121">Рассматриваются вопросы задания квот, доступных на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="2bb9b-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="2bb9b-122">Работа со средствами NAT и брандмауэрами</span><span class="sxs-lookup"><span data-stu-id="2bb9b-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="2bb9b-123">Описывается настройка транспортного уровня при отправке или получении сообщений за брандмауэром или при использовании преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="2bb9b-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="2bb9b-124">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="2bb9b-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="2bb9b-125">Описывается использование компонента общего доступа к портам Net.TCP системы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bb9b-125">Describes how to use the Net.TCP Port Sharing component of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2bb9b-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="2bb9b-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="2bb9b-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2bb9b-127">Related Sections</span></span>  
 [<span data-ttu-id="2bb9b-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="2bb9b-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="2bb9b-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="2bb9b-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
