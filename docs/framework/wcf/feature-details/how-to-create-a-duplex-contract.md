---
title: "Практическое руководство. Создание дуплексного контракта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30fc31055563db75512639bf7fb3b9119be280e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-duplex-contract"></a>Практическое руководство. Создание дуплексного контракта
В этом разделе приведены основные этапы создания методов, использующих дуплексные (двухсторонние) контракты. Дуплексный контракт позволяет клиентам и серверам взаимодействовать друг с другом независимо (клиент может инициировать вызовы сервера, а сервер - вызовы клиента). Дуплексный контракт - это одна из трех схем обмена сообщениями, доступных для служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Две другие схемы обмена сообщениями - это односторонний обмен и запрос-ответ. Дуплексный контракт состоит из двух односторонних контрактов между клиентом и сервером, при этом не требуется корреляция между вызовами методов. Контракт этого типа следует использовать, если служба должна запрашивать у клиента дополнительную информацию или в явном виде создавать события в клиенте. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Создание клиентского приложения для дуплексного контракта, в разделе [как: службы доступа с дуплексным контрактом](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md). Работающий пример см. в разделе [дуплексного](../../../../docs/framework/wcf/samples/duplex.md) образца.  
  
### <a name="to-create-a-duplex-contract"></a>Создание двухстороннего контракта  
  
1.  Создайте интерфейс, образующий серверную часть дуплексного контракта.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3.  Объявите в интерфейсе подписи методов.  
  
4.  Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждой подписи метода, которая должна входить в открытый контракт.  
  
5.  Создайте интерфейс обратного вызова, определяющий набор операций, которые служба может вызывать в клиенте.  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6.  Объявите подписи методов в интерфейсе обратного вызова.  
  
7.  Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждой подписи метода, которая должна входить в открытый контракт.  
  
8.  Объедините эти два интерфейса в дуплексный контракт, задав для свойства <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> в основном интерфейсе тип интерфейса обратного вызова.  
  
### <a name="to-call-methods-on-the-client"></a>Вызов методов в клиенте  
  
1.  В реализации основного контракта на стороне службы объявите переменную для интерфейса обратного вызова.  
  
2.  Присвойте переменной ссылку на объект, возвращаемый методом <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> класса <xref:System.ServiceModel.OperationContext>.  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3.  Вызовите методы, определенные в интерфейсе обратного вызова.  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется дуплексное взаимодействие. Контракт службы содержит операции службы для перемещения вперед или назад. Контракт клиента содержит операцию службы для сообщения о положении.  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> обеспечивает автоматическое создание определения контракта службы в языке описания служб (WSDL).  
  
-   Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для получения WSDL-документ и (необязательно) код и конфигурацию для клиента.  
  
-   Конечные точки, предоставляющие дуплексные службы, должны быть безопасными. Когда служба получает дуплексное сообщение, она проверяет элемент ReplyTo входящего сообщения, чтобы определить, куда отправлять ответ. Если канал не является безопасным, ненадежный клиент может послать вредоносное сообщение с указанием компьютера для атаки в элементе ReplyTo, что приведет к атаке типа "отказ в обслуживании" на этот компьютер. В случае обычной передачи сообщений по схеме "запрос-ответ" это не является проблемой, так как элемент ReplyTo игнорируется, а ответное сообщение передается по тому каналу, по которому поступило исходное сообщение.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [Как: доступ к службам с дуплексным контрактом](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Дуплекс](../../../../docs/framework/wcf/samples/duplex.md)  
 [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [Практическое руководство. Определение контракта службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [Сеанс](../../../../docs/framework/wcf/samples/session.md)
