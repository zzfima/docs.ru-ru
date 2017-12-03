---
title: Message Encoding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b0147049a988a8fa2d0721da39f1d9c37278803
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="message-encoding"></a><span data-ttu-id="9d3c2-102">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="9d3c2-102">Message Encoding</span></span>
<span data-ttu-id="9d3c2-103">Кодирование - это процесс преобразования набора символов Юникода в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="9d3c2-104">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-104">Decoding is the reverse process.</span></span> <span data-ttu-id="9d3c2-105">В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="9d3c2-106">В разделе конфигурации `binaryMessageEncoding` указывается кодировка символов и управление версиями сообщений, используемые для двоичных сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="9d3c2-107">Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="9d3c2-108">Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-*.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
 <span data-ttu-id="9d3c2-109">В разделе конфигурации `mtomMessageEncoding` указывается кодировка символов и управление версиями сообщений, используемые для сообщения с помощью кодирования MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="9d3c2-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="9d3c2-110">MTOM - это эффективная технология для передачи двоичных данных в сообщениях Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="9d3c2-111">Кодировщик MTOM предпринимает попытку соблюсти баланс между эффективностью и взаимодействием.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="9d3c2-112">Кодирование MTOM передает большую часть XML-данных в текстовой форме, но оптимизирует большие блоки двоичных данных путем передачи их в исходном виде, без преобразования в текст.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="9d3c2-113">В разделе конфигурации `textMessageEncoding` указывается кодировщик текста, используемый для создания текстовых сообщений в сети.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="9d3c2-114">Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-*.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-114">Messages produced by this encoder are suitable for WS-* based interop.</span></span> <span data-ttu-id="9d3c2-115">Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="9d3c2-116">Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="9d3c2-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3c2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9d3c2-117">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [<span data-ttu-id="9d3c2-118">Привязки</span><span class="sxs-lookup"><span data-stu-id="9d3c2-118">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9d3c2-119">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="9d3c2-119">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="9d3c2-120">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="9d3c2-120">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="9d3c2-121">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9d3c2-121">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="9d3c2-122">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="9d3c2-122">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
