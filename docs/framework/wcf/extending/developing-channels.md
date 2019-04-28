---
title: Разработка каналов
ms.date: 03/30/2017
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
ms.openlocfilehash: 44fb0da52c60b900c41b7b497861c12ed72d8ffc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858069"
---
# <a name="developing-channels"></a>Разработка каналов
Для разработки протокола или транспорта канала, который может использоваться с Windows Communication Foundation (WCF) уровня приложений необходимо выполнить несколько действий. В этом разделе описываются эти действия и указываются конкретные разделы для получения дополнительных сведений. Чтобы понять модель каналов и различных типов, описанных в этом разделе, см. в разделе [Общие сведения о модели каналов](../../../../docs/framework/wcf/extending/channel-model-overview.md). Пример канала транспорта полный, см. в разделе [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>Список задач разработки канала  
 Чтобы создать канал, определенный пользователем, выполните следующие действия (для всех каналов).  
  
1. Решите, какой из шаблонов обмена сообщениями по каналу (<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IReplyChannel>) будет поддерживаться фабрикой <xref:System.ServiceModel.Channels.IChannelFactory> и прослушивателем <xref:System.ServiceModel.Channels.IChannelListener>, а также, будет ли этот шаблон поддерживать связанные с сеансами разновидности указанных интерфейсов. Дополнительные сведения см. в разделе [Выбор шаблона обмена сообщениями](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md).  
  
2. Создайте фабрику и прослушиватель каналов (<xref:System.ServiceModel.Channels.IChannelFactory> и <xref:System.ServiceModel.Channels.IChannelListener>), которые поддерживают выбранный шаблон обмена сообщениями. Сведения о разработке фабрик см. в разделе [клиента: Фабрики каналов и каналы](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md). Сведения о разработке прослушивателей см. в разделе [службы: Прослушиватели каналов и каналы](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md).  
  
3. Обеспечьте, чтобы любые исключения, связанные с сетью, нормализовались либо в <xref:System.TimeoutException?displayProperty=nameWithType>, либо в соответствующий класс, унаследованный от <xref:System.ServiceModel.CommunicationException>. Дополнительные сведения см. в разделе [обработки исключений и ошибок](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
4. Чтобы разрешить использование из прикладного уровня, добавьте элемент <xref:System.ServiceModel.Channels.BindingElement>, добавляющий пользовательский канал в стек каналов. Дополнительные сведения см. в разделе [Создание элемента привязки BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md).  
  
 Чтобы включить более полную поддержку на прикладном уровне, необходимо выполнить следующие дополнительные действия.  
  
1. Добавьте раздел расширения элементов привязки, чтобы представить новый элемент привязки системе конфигурации. Дополнительные сведения см. в разделе [конфигурация и поддержка метаданных](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
2. Добавьте расширения метаданных, чтобы сообщить о возможностях в другие конечные точки. Дополнительные сведения см. в разделе [конфигурация и поддержка метаданных](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
3. Добавьте привязку, которая предварительно настраивает стек элементов привязки в соответствии с четко определенным профилем. Дополнительные сведения см. в разделе [параметрах привязок](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
4. Добавьте раздел привязки и элемент конфигурации привязки, чтобы представить привязку системе конфигурации. Дополнительные сведения см. в разделе [конфигурация и поддержка метаданных](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
## <a name="see-also"></a>См. также

- [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
