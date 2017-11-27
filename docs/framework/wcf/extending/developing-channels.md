---
title: "Разработка каналов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dd33f987ab28b42c16aa4798c59675225dcaf520
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="developing-channels"></a>Разработка каналов
Для разработки протокола или канала транспорта, который может использоваться с [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], прикладной уровень требует выполнения нескольких действий. В этом разделе описываются эти действия и указываются конкретные разделы для получения дополнительных сведений. Чтобы понять модель канала и различных типов, описанных в этом разделе, см. [Общие сведения о модели каналов](../../../../docs/framework/wcf/extending/channel-model-overview.md). Пример завершения транспорта канала, см. [транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>Список задач разработки канала  
 Чтобы создать канал, определенный пользователем, выполните следующие действия (для всех каналов).  
  
1.  Решите, какой из шаблонов обмена сообщениями по каналу (<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IReplyChannel>) будет поддерживаться фабрикой <xref:System.ServiceModel.Channels.IChannelFactory> и прослушивателем <xref:System.ServiceModel.Channels.IChannelListener>, а также, будет ли этот шаблон поддерживать связанные с сеансами разновидности указанных интерфейсов. Дополнительные сведения см. в разделе [Выбор шаблона обмена сообщениями](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md).  
  
2.  Создайте фабрику и прослушиватель каналов (<xref:System.ServiceModel.Channels.IChannelFactory> и <xref:System.ServiceModel.Channels.IChannelListener>), которые поддерживают выбранный шаблон обмена сообщениями. Дополнительные сведения о разработке фабрик см. [клиент: фабрики каналов и каналы](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md). Дополнительные сведения о разработке прослушивателей см. в разделе [служба: прослушиватели каналов и каналы](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md).  
  
3.  Обеспечьте, чтобы любые исключения, связанные с сетью, нормализовались либо в <xref:System.TimeoutException?displayProperty=nameWithType>, либо в соответствующий класс, унаследованный от <xref:System.ServiceModel.CommunicationException>. Дополнительные сведения см. в разделе [обработки исключений и сбоев](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
4.  Чтобы разрешить использование из прикладного уровня, добавьте элемент <xref:System.ServiceModel.Channels.BindingElement>, добавляющий пользовательский канал в стек каналов. Дополнительные сведения см. в разделе [Создание элемента привязки BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md).  
  
 Чтобы включить более полную поддержку на прикладном уровне, необходимо выполнить следующие дополнительные действия.  
  
1.  Добавьте раздел расширения элементов привязки, чтобы представить новый элемент привязки системе конфигурации. Дополнительные сведения см. в разделе [конфигурация и поддержка метаданных](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
2.  Добавьте расширения метаданных, чтобы сообщить о возможностях в другие конечные точки. Дополнительные сведения см. в разделе [конфигурация и поддержка метаданных](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
3.  Добавьте привязку, которая предварительно настраивает стек элементов привязки в соответствии с четко определенным профилем. Дополнительные сведения см. в разделе [привязки привязанных к](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
4.  Добавьте раздел привязки и элемент конфигурации привязки, чтобы представить привязку системе конфигурации. Дополнительные сведения см. в разделе [конфигурация и поддержка метаданных](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
## <a name="see-also"></a>См. также  
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
