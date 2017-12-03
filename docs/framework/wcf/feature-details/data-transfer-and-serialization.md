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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29ca4041e24a99546dfb665b0ce9e695732442d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="data-transfer-and-serialization"></a>Передача данных и сериализация
В распределенных системах для выполнения каких-либо задач клиенты и службы обмениваются данными. Разработчики служб и клиентов должны понимать принципы обработки и сериализации данных в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], чтобы создавать эффективные и простые в обслуживании приложения.  
  
## <a name="in-this-section"></a>Содержание  
 [Specifying Data Transfer in Service Contracts](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 Базовые принципы передачи данных в службах.  
  
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 Понятие контрактов данных и процедур их создания и использования.  
  
 [Сериализатор контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 Сериализация данных с помощью класса <xref:System.Runtime.Serialization.DataContractSerializer> и каких-либо расширений класса <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 [С помощью класса XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 Способы и причины использования класса <xref:System.Xml.Serialization.XmlSerializer> в качестве альтернативы классу <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 [Использование контрактов сообщений](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 Точное управление сообщениями SOAP с помощью контрактов сообщений.  
  
 [Использование класса сообщений](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 Использование возможностей класса Message.  
  
 [Фильтрация](../../../../docs/framework/wcf/feature-details/filtering.md)  
 Фильтрация, позволяющая выполнять предварительную обработку сообщений на основе различных критериев.  
  
 [Большие объемы данных и потоковой передачи](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 Отправка больших фрагментов данных, например двоичных файлов.  
  
 [Вопросы безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 Вопросы, которые необходимо учитывать при решении задач сериализации и передачи данных.  
  
 [Общие сведения об архитектуре передачи данных](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 Обзор архитектуры передачи данных в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Расширение кодировщиков и сериализаторов](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>См. также  
 [Рекомендации. Управление версиями контракта данных](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [Управление версиями служб](../../../../docs/framework/wcf/service-versioning.md)
