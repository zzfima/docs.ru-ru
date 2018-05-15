---
title: Транспорты в Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="072c0-102">Транспорты в Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="072c0-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="072c0-103">Транспортный уровень является самым нижним уровнем стека каналов.</span><span class="sxs-lookup"><span data-stu-id="072c0-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="072c0-104">Основными транспортами, используемыми в Windows Communication Foundation (WCF), HTTP, HTTPS, TCP и именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="072c0-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="072c0-105">В подразделах данного раздела рассматриваются выбор типа транспорта среди названных выше типов, настройка транспорта и задание свойств настройки.</span><span class="sxs-lookup"><span data-stu-id="072c0-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="072c0-106">WCF содержит дополнительные типы транспорта.</span><span class="sxs-lookup"><span data-stu-id="072c0-106">WCF includes additional transports.</span></span> <span data-ttu-id="072c0-107">Сведения о транспорта очереди сообщений (MSMQ) см. в разделе [очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="072c0-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="072c0-108">Сведения о транспорта одноранговая сеть, в разделе [-одноранговые сети](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="072c0-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="072c0-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="072c0-109">In This Section</span></span>  
 [<span data-ttu-id="072c0-110">Выбор транспорта</span><span class="sxs-lookup"><span data-stu-id="072c0-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="072c0-111">Описываются три основных типа транспорта и рассматриваются вопросы выбора транспорта.</span><span class="sxs-lookup"><span data-stu-id="072c0-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="072c0-112">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="072c0-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="072c0-113">Описываются факторы, которые необходимо принять во внимание при выборе элемента привязки для кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="072c0-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="072c0-114">Потоковая передача сообщений</span><span class="sxs-lookup"><span data-stu-id="072c0-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="072c0-115">Описывается настройка транспортного уровня для выполнения потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="072c0-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="072c0-116">Настройка HTTP и HTTPS</span><span class="sxs-lookup"><span data-stu-id="072c0-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="072c0-117">Описывается настройка элементов привязки транспорта HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="072c0-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="072c0-118">Практическое руководство. Замена резервирования URL с помощью WCF на ограниченное резервирование</span><span class="sxs-lookup"><span data-stu-id="072c0-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="072c0-119">Описывает использование WCFURL ограничен резервирования.</span><span class="sxs-lookup"><span data-stu-id="072c0-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="072c0-120">Квоты транспорта</span><span class="sxs-lookup"><span data-stu-id="072c0-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="072c0-121">Рассматриваются вопросы задания квот, доступных на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="072c0-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="072c0-122">Работа со средствами NAT и брандмауэрами</span><span class="sxs-lookup"><span data-stu-id="072c0-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="072c0-123">Описывается настройка транспортного уровня при отправке или получении сообщений за брандмауэром или при использовании преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="072c0-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="072c0-124">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="072c0-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="072c0-125">Описывает использование компонента общего доступа к портам Net.TCP (WCF).</span><span class="sxs-lookup"><span data-stu-id="072c0-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="072c0-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="072c0-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="072c0-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="072c0-127">Related Sections</span></span>  
 [<span data-ttu-id="072c0-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="072c0-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="072c0-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="072c0-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
