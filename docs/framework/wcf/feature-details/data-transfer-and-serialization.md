---
title: Передача данных и сериализация
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 53c1421bf14c598611e116c61353c4ecd465f1aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="faaa2-102">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="faaa2-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="faaa2-103">В распределенных системах для выполнения каких-либо задач клиенты и службы обмениваются данными.</span><span class="sxs-lookup"><span data-stu-id="faaa2-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="faaa2-104">Как разработчик службы или клиента необходимо также понять, как Windows Communication Foundation (WCF) обрабатывает и сериализации данных для создания приложений, которые эффективны и простые в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="faaa2-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="faaa2-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="faaa2-105">In This Section</span></span>  
 [<span data-ttu-id="faaa2-106">Задание передачи данных в контрактах служб</span><span class="sxs-lookup"><span data-stu-id="faaa2-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="faaa2-107">Базовые принципы передачи данных в службах.</span><span class="sxs-lookup"><span data-stu-id="faaa2-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="faaa2-108">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="faaa2-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="faaa2-109">Понятие контрактов данных и процедур их создания и использования.</span><span class="sxs-lookup"><span data-stu-id="faaa2-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="faaa2-110">Сериализатор контракта данных</span><span class="sxs-lookup"><span data-stu-id="faaa2-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="faaa2-111">Сериализация данных с помощью класса <xref:System.Runtime.Serialization.DataContractSerializer> и каких-либо расширений класса <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="faaa2-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="faaa2-112">Использование класса XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="faaa2-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="faaa2-113">Способы и причины использования класса <xref:System.Xml.Serialization.XmlSerializer> в качестве альтернативы классу <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="faaa2-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="faaa2-114">Использование контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="faaa2-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="faaa2-115">Точное управление сообщениями SOAP с помощью контрактов сообщений.</span><span class="sxs-lookup"><span data-stu-id="faaa2-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="faaa2-116">Использование класса сообщений</span><span class="sxs-lookup"><span data-stu-id="faaa2-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="faaa2-117">Использование возможностей класса Message.</span><span class="sxs-lookup"><span data-stu-id="faaa2-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="faaa2-118">Фильтрация</span><span class="sxs-lookup"><span data-stu-id="faaa2-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="faaa2-119">Фильтрация, позволяющая выполнять предварительную обработку сообщений на основе различных критериев.</span><span class="sxs-lookup"><span data-stu-id="faaa2-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="faaa2-120">Большие наборы данных и потоковая передача</span><span class="sxs-lookup"><span data-stu-id="faaa2-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="faaa2-121">Отправка больших фрагментов данных, например двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="faaa2-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="faaa2-122">Вопросы безопасности для данных</span><span class="sxs-lookup"><span data-stu-id="faaa2-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="faaa2-123">Вопросы, которые необходимо учитывать при решении задач сериализации и передачи данных.</span><span class="sxs-lookup"><span data-stu-id="faaa2-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="faaa2-124">Общие сведения об архитектуре передачи данных</span><span class="sxs-lookup"><span data-stu-id="faaa2-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="faaa2-125">Содержит описание представления обзор архитектуры передачи данных в WCF.</span><span class="sxs-lookup"><span data-stu-id="faaa2-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="faaa2-126">Ссылка</span><span class="sxs-lookup"><span data-stu-id="faaa2-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="faaa2-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="faaa2-127">Related Sections</span></span>  
 [<span data-ttu-id="faaa2-128">Расширение кодировщиков и сериализаторов</span><span class="sxs-lookup"><span data-stu-id="faaa2-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="faaa2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="faaa2-129">See Also</span></span>  
 [<span data-ttu-id="faaa2-130">Рекомендации. Управление версиями контракта данных</span><span class="sxs-lookup"><span data-stu-id="faaa2-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="faaa2-131">Управление версиями служб</span><span class="sxs-lookup"><span data-stu-id="faaa2-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
