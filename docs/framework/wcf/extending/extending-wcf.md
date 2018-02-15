---
title: "Расширение WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c84f25dfd5d3066f9c5d0b62bc0b28bc98c283d
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="extending-wcf"></a>Расширение WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет изменять и расширять компоненты времени выполнения для точного управления и расширения приложений на основе служб. Статьи данного раздела подробно описывают архитектуру расширяемости. Дополнительные сведения о базовое программирование в разделе [базовое Программирование WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Расширение ServiceHost и уровень модели службы](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 Уровень модели службы отвечает за удаление входящих сообщений из базовых каналов, их перевод в вызовы метода в коде приложения и отправку результатов обратно вызывающему коду.  Расширения модели службы изменяют или реализуют порядок и компоненты выполнения или взаимодействия, в том числе компоненты, включающие возможности диспетчера, пользовательские поведения, перехват сообщений и параметров, а также другие расширяемые возможности.  
  
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 Привязки - это объекты, которые описывают сведения о связи, требуемые для подключения к конечной точке. Расширения привязок и пользовательские привязки реализуют пользовательскую функциональность связи, необходимую для поддержки возможностей приложения.  
  
 [Расширение уровня каналов](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 Уровень канала находится в уровне модели службы и отвечает за обмен сообщениями между клиентами и службами. Расширения каналов могут реализовывать новые функциональные возможности протокола, такие как безопасность. Они также реализуют транспортные функциональные возможности, такие как новый сетевой транспорт для передачи сообщений SOAP.  
  
 [Расширение безопасности](../../../../docs/framework/wcf/extending/extending-security.md)  
 Безопасность в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] состоит из транспортной безопасности (целостности, конфиденциальности и проверки подлинности), управления доступом и аудита. Классы, находящиеся в пространстве имен `IdentityModel`, используются [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для управления доступом. Понимание архитектуры безопасности позволяет создавать пользовательские типы утверждений для использования в системах управления доступом.  
  
 [Расширение системы метаданных](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 Система метаданных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является набором классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб. Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.  
  
 [Расширение кодировщиков и сериализаторов](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 Кодировщики и сериализаторы преобразовывают данные из одной формы в другую. Статьи данного раздела описывают, как расширять переданные классы для удовлетворения конкретных требований.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Базовое программирование для WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [Подробные сведения о возможностях WCF](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [Правила и рекомендации](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
