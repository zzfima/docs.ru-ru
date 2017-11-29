---
title: "Передача данных и сериализация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41357c9a039414ac692bac69337b2963d5c6b341
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="da381-102">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="da381-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="da381-103">В распределенных системах для выполнения каких-либо задач клиенты и службы обмениваются данными.</span><span class="sxs-lookup"><span data-stu-id="da381-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="da381-104">Разработчики служб и клиентов должны понимать принципы обработки и сериализации данных в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], чтобы создавать эффективные и простые в обслуживании приложения.</span><span class="sxs-lookup"><span data-stu-id="da381-104">As a developer of a service or client, you must also understand how [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da381-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="da381-105">In This Section</span></span>  
 [<span data-ttu-id="da381-106">Specifying Data Transfer in Service Contracts</span><span class="sxs-lookup"><span data-stu-id="da381-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="da381-107">Базовые принципы передачи данных в службах.</span><span class="sxs-lookup"><span data-stu-id="da381-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="da381-108">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="da381-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="da381-109">Понятие контрактов данных и процедур их создания и использования.</span><span class="sxs-lookup"><span data-stu-id="da381-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="da381-110">Сериализатор контракта данных</span><span class="sxs-lookup"><span data-stu-id="da381-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="da381-111">Сериализация данных с помощью класса <xref:System.Runtime.Serialization.DataContractSerializer> и каких-либо расширений класса <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="da381-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="da381-112">С помощью класса XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="da381-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="da381-113">Способы и причины использования класса <xref:System.Xml.Serialization.XmlSerializer> в качестве альтернативы классу <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="da381-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="da381-114">Использование контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="da381-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="da381-115">Точное управление сообщениями SOAP с помощью контрактов сообщений.</span><span class="sxs-lookup"><span data-stu-id="da381-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="da381-116">Использование класса сообщений</span><span class="sxs-lookup"><span data-stu-id="da381-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="da381-117">Использование возможностей класса Message.</span><span class="sxs-lookup"><span data-stu-id="da381-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="da381-118">Фильтрация</span><span class="sxs-lookup"><span data-stu-id="da381-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="da381-119">Фильтрация, позволяющая выполнять предварительную обработку сообщений на основе различных критериев.</span><span class="sxs-lookup"><span data-stu-id="da381-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="da381-120">Большие объемы данных и потоковой передачи</span><span class="sxs-lookup"><span data-stu-id="da381-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="da381-121">Отправка больших фрагментов данных, например двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="da381-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="da381-122">Вопросы безопасности для данных</span><span class="sxs-lookup"><span data-stu-id="da381-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="da381-123">Вопросы, которые необходимо учитывать при решении задач сериализации и передачи данных.</span><span class="sxs-lookup"><span data-stu-id="da381-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="da381-124">Общие сведения об архитектуре передачи данных</span><span class="sxs-lookup"><span data-stu-id="da381-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="da381-125">Обзор архитектуры передачи данных в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da381-125">Describes a view of the overall design of data transfer in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da381-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="da381-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="da381-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="da381-127">Related Sections</span></span>  
 [<span data-ttu-id="da381-128">Расширение кодировщиков и сериализаторов</span><span class="sxs-lookup"><span data-stu-id="da381-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="da381-129">См. также</span><span class="sxs-lookup"><span data-stu-id="da381-129">See Also</span></span>  
 [<span data-ttu-id="da381-130">Рекомендации. Управление версиями контракта данных</span><span class="sxs-lookup"><span data-stu-id="da381-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="da381-131">Управление версиями служб</span><span class="sxs-lookup"><span data-stu-id="da381-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
