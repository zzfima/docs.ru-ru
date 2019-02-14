---
title: Пользовательские привязки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: e3954e90ed091d03656f25ce1a9b1ff35ffaa9ea
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260729"
---
# <a name="custom-bindings"></a><span data-ttu-id="05f77-102">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="05f77-102">Custom Bindings</span></span>
<span data-ttu-id="05f77-103">Класс <xref:System.ServiceModel.Channels.CustomBinding> можно использовать, когда ни одна из системных привязок не соответствует требованиям службы.</span><span class="sxs-lookup"><span data-stu-id="05f77-103">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="05f77-104">Все привязки создаются из упорядоченных наборов элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="05f77-104">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="05f77-105">Пользовательские привязки можно создавать из набора предоставляемых системой элементов привязки или в них можно включать определяемые пользователем элементы привязки.</span><span class="sxs-lookup"><span data-stu-id="05f77-105">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="05f77-106">Пользовательские элементы привязки можно применять, например, для использования в конечной точке службы новых транспортов или кодировщиков.</span><span class="sxs-lookup"><span data-stu-id="05f77-106">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="05f77-107">Рабочие примеры см. в разделе [примеры привязки Custom](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="05f77-107">For working examples, see [Custom Binding Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span></span> <span data-ttu-id="05f77-108">Дополнительные сведения см. в разделе [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="05f77-108">For more information, see [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="05f77-109">Создание пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="05f77-109">Construction of a Custom Binding</span></span>  
 <span data-ttu-id="05f77-110">Пользовательские привязки создаются с использованием одного из конструкторов <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> из коллекции элементов привязки, которые располагаются в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="05f77-110">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="05f77-111">Вверху расположен необязательный класс <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, который разрешает поток транзакций.</span><span class="sxs-lookup"><span data-stu-id="05f77-111">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="05f77-112">Далее следует необязательный класс <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, который обеспечивает сеанс и механизмы сортировки, в соответствии со спецификацией WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="05f77-112">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="05f77-113">Сеанс может включать посредников SOAP и транспорта.</span><span class="sxs-lookup"><span data-stu-id="05f77-113">A session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="05f77-114">Далее следует необязательный класс <xref:System.ServiceModel.Channels.SecurityBindingElement>, который предоставляет возможности безопасности, такие как авторизация, проверка подлинности, защита и конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="05f77-114">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>  
  
-   <span data-ttu-id="05f77-115">Далее следует необязательный класс <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>, который обеспечивает возможность двусторонней дуплексной связи с транспортным протоколом, изначально не поддерживающим дуплексную связь, таким как HTTP.</span><span class="sxs-lookup"><span data-stu-id="05f77-115">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>  
  
-   <span data-ttu-id="05f77-116">Далее следует необязательный класс <xref:System.ServiceModel.Channels.OneWayBindingElement>), который обеспечивает одностороннюю связь.</span><span class="sxs-lookup"><span data-stu-id="05f77-116">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>  
  
-   <span data-ttu-id="05f77-117">Далее следует обязательный элемент привязки безопасности потока, который может быть одним из следующих.</span><span class="sxs-lookup"><span data-stu-id="05f77-117">Next is an optional stream security binding element which can be one of the following.</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="05f77-118">Далее следует обязательный элемент привязки для кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="05f77-118">Next is a required message encoding binding element.</span></span> <span data-ttu-id="05f77-119">Можно использовать свой кодировщик транспорта или одну из трех привязок кодировки сообщений:</span><span class="sxs-lookup"><span data-stu-id="05f77-119">You can use your own message encoder or one of the three message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
 <span data-ttu-id="05f77-120">Внизу расположен обязательный элемент транспорта.</span><span class="sxs-lookup"><span data-stu-id="05f77-120">At the bottom is a required transport element.</span></span> <span data-ttu-id="05f77-121">Можно использовать собственный транспорт или один из следующих элементов привязки транспорта, предоставляемых Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="05f77-121">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>  
  
-   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
-   <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
 <span data-ttu-id="05f77-122">В следующей таблице приведены сводные данные по параметрам каждого уровня.</span><span class="sxs-lookup"><span data-stu-id="05f77-122">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="05f77-123">Уровень</span><span class="sxs-lookup"><span data-stu-id="05f77-123">Layer</span></span>|<span data-ttu-id="05f77-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="05f77-124">Options</span></span>|<span data-ttu-id="05f77-125">Обязательно</span><span class="sxs-lookup"><span data-stu-id="05f77-125">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="05f77-126">Транзакции</span><span class="sxs-lookup"><span data-stu-id="05f77-126">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="05f77-127">Нет</span><span class="sxs-lookup"><span data-stu-id="05f77-127">No</span></span>|  
|<span data-ttu-id="05f77-128">Надежность</span><span class="sxs-lookup"><span data-stu-id="05f77-128">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="05f77-129">Нет</span><span class="sxs-lookup"><span data-stu-id="05f77-129">No</span></span>|  
|<span data-ttu-id="05f77-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="05f77-130">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="05f77-131">Нет</span><span class="sxs-lookup"><span data-stu-id="05f77-131">No</span></span>|  
|<span data-ttu-id="05f77-132">кодировка</span><span class="sxs-lookup"><span data-stu-id="05f77-132">Encoding</span></span>|<span data-ttu-id="05f77-133">Текст, двоичное, механизм оптимизации передачи сообщений (MTOM), пользовательское</span><span class="sxs-lookup"><span data-stu-id="05f77-133">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="05f77-134">Да</span><span class="sxs-lookup"><span data-stu-id="05f77-134">Yes</span></span>|  
|<span data-ttu-id="05f77-135">Transport</span><span class="sxs-lookup"><span data-stu-id="05f77-135">Transport</span></span>|<span data-ttu-id="05f77-136">TCP, HTTP, HTTPS, именованные каналы (также называются IPC), одноранговый (P2P), очередь сообщений (также называется MSMQ), пользовательский</span><span class="sxs-lookup"><span data-stu-id="05f77-136">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="05f77-137">Да</span><span class="sxs-lookup"><span data-stu-id="05f77-137">Yes</span></span>|  
  
 <span data-ttu-id="05f77-138">Кроме того, можно определить собственные элементы привязки и вставить их между любыми из приведенных выше заданных уровней.</span><span class="sxs-lookup"><span data-stu-id="05f77-138">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f77-139">См. также</span><span class="sxs-lookup"><span data-stu-id="05f77-139">See also</span></span>
- [<span data-ttu-id="05f77-140">Общие сведения о создании конечных точек</span><span class="sxs-lookup"><span data-stu-id="05f77-140">Endpoint Creation Overview</span></span>](../../../../docs/framework/wcf/endpoint-creation-overview.md)
- [<span data-ttu-id="05f77-141">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="05f77-141">Using Bindings to Configure Services and Clients</span></span>](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="05f77-142">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="05f77-142">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="05f77-143">Практическое руководство. Настройка привязки, предоставляемой системой</span><span class="sxs-lookup"><span data-stu-id="05f77-143">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
- [<span data-ttu-id="05f77-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="05f77-144">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="05f77-145">Пользовательская привязка</span><span class="sxs-lookup"><span data-stu-id="05f77-145">Custom Binding</span></span>](../../../../docs/framework/wcf/samples/custom-binding.md)
