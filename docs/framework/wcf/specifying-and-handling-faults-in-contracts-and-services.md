---
title: "Задание и обработка сбоев в контрактах и службах"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57fc01b77379389ca4d86d241ec8f3d672b519b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>Задание и обработка сбоев в контрактах и службах
Приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] обрабатывают ошибки, сопоставляя объекты управляемых исключений с объектами ошибок SOAP и наоборот. В подразделах этого раздела описывается, как разрабатывать контракты, чтобы представлять ошибки в виде пользовательских ошибок SOAP, как возвращать эти ошибки в реализации службы, и как клиенты могут перехватывать такие ошибки.  
  
## <a name="error-handling-overview"></a>Общие сведения об обработке ошибок  
 Во всех управляемых приложениях обработка ошибок представлена объектами <xref:System.Exception>. В приложениях, основанных на протоколе SOAP, таких как [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], методы службы передают информацию об ошибке обработки с помощью сообщений об ошибке протокола SOAP. Сообщения об ошибках SOAP являются типами сообщения, которые включаются в метаданные, связанные с работой службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы. Кроме того, поскольку сообщения о неисправностях передаются клиентам в формате XML, система поддерживает возможность взаимодействия, которая может использоваться клиентами на любой платформе SOAP, расширяя функциональность приложения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Поскольку приложения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] выполняются в обоих типах систем ошибок, любые сведения управляемых исключений, отправляемые клиенту, должны быть преобразованы в ошибки SOAP в службе, а также отправлены и преобразованы из ошибок SOAP в исключения ошибок в клиентах [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. В случае дуплексных клиентов клиентские контракты могут отправлять ошибки SOAP обратно в службу. В обоих случаях можно использовать поведения исключений для службы по умолчанию или можно явно управлять тем, будут ли исключения сопоставляться с сообщениями об ошибке и как будет выполняться это сопоставление.  
  
 Можно отправлять два типа ошибок SOAP: *объявлен* и *необъявленный*. Объявленные ошибки SOAP представляют ошибки, в которых в операции имеется атрибут <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>, указывающий пользовательский тип ошибки SOAP. *Необъявленный* ошибок SOAP не указаны в контракте операции.  
  
 Настоятельно рекомендуется, чтобы операции службы объявляли свои ошибки с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute>. Это позволит формально указать все ошибки SOAP, которые клиент может получить во время обычной операции. Кроме того, чтобы свести к минимум раскрытие информации, рекомендуется возвращать в ошибке SOAP только те сведения, которые необходимо знать клиенту.  
  
 Обычно службы (и дуплексные клиенты) выполняют следующие шаги, чтобы интегрировать обработку в свои приложения.  
  
-   Сопоставление исключений и пользовательскими ошибками SOAP.  
  
-   Клиенты и службы отправляют и получают ошибки SOAP в виде исключений.  
  
 Кроме того, клиенты и службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] могут использовать необъявленные ошибки SOAP в целях отладки, а также расширять поведение при ошибках по умолчанию. В следующих разделах рассматриваются эти задачи и принципы.  
  
## <a name="map-exceptions-to-soap-faults"></a>Сопоставление исключений с ошибками SOAP  
 Первым шагом в создании операции, обрабатывающей ошибки, является определение условий, при которых клиентское приложение должно быть проинформировано об ошибках. Для некоторых операций имеются ошибки, относящиеся к их функциональности. Например, операция `PurchaseOrder` может возвратить конкретную информацию клиенту, которому больше не разрешено размещать заказ на покупку. В других случаях, например в службе `Calculator`, более общая ошибка SOAP `MathFault` может описать все условия ошибки во всей службе. После определения ошибок клиентов может быть создана пользовательская ошибка SOAP. Кроме того, можно отметить, что операция возвращает данную эту ошибку при возникновении соответствующей ошибки.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Этот шаг по разработке службы или клиента, в разделе [определение и указание ошибок](../../../docs/framework/wcf/defining-and-specifying-faults.md).  
  
## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>Клиенты и службы обрабатывают ошибки SOAP в виде исключений  
 Идентификация ошибок операции, определение пользовательских ошибок SOAP и пометка операций, которые возвращают эти ошибки, являются первыми шагами для успешной обработки ошибок в приложениях [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Следующий шаг заключается в надлежащей реализации отправки и получения этих ошибок. Обычно службы отправляют сообщения об ошибках, чтобы информировать клиентские приложения, но дуплексные клиенты также могут отправлять службам сообщения об ошибках протокола SOAP.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Отправки и получения ошибки](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="undeclared-soap-faults-and-debugging"></a>Необъявленные ошибки протокола SOAP и отладка  
 Объявленные ошибки протокола SOAP очень полезны для построения надежных распределенных приложений с возможностью взаимодействия. Однако в некоторых случаях для службы (или дуплексного клиента) полезно отправлять необъявленную ошибку SOAP, которая не упоминается для данной операции в языке WSDL. Например, при разработке службы могут произойти непредвиденные ситуации, в которых для отладки понадобится отправить информацию обратно клиенту. Кроме того, для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> можно задать значение `true`, чтобы разрешить клиентам [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] получать информацию о внутренних исключениях операции службы. Отправка отдельных ошибок и задание свойств отладки поведения описаны в [отправка и получение ошибки](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
> [!IMPORTANT]
>  Поскольку управляемые исключения могут предоставлять внутренние сведения о приложении, задание для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> значения `true` позволяет клиентам [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] получать информацию о внутренних исключениях операций службы, включая персонально идентифицируемую и другую конфиденциальную информацию.  
>   
>  Присваивать свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> значение `true` рекомендуется только в качестве временного способа отладки приложения службы. Кроме того, WSDL для метода, который возвращает такие необработанные управляемые исключения, не содержит контракт для исключения <xref:System.ServiceModel.FaultException%601> типа <xref:System.ServiceModel.ExceptionDetail>. В клиентах должна быть предусмотрена возможность получения неизвестной ошибки SOAP (возвращаемой клиентам [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в виде объектов <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>) для надлежащего получения отладочной информации.  
  
## <a name="customizing-error-handling-with-ierrorhandler"></a>Настройка обработки ошибок с помощью интерфейса IErrorHandler  
 Если имеются особые требования для настройки ответного сообщения клиента при возникновении исключения на уровне приложения или выполнения специальной обработки после возвращения ответного сообщения, реализуйте интерфейс <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType>.  
  
## <a name="fault-serialization-issues"></a>Проблемы сериализации сбоя  
 При десериализации контракта сбоя службы WCF прежде всего пытаются сопоставить имя контракта сбоя в сообщении протокола SOAP с типом контракта сбоя. Если точное соответствие не обнаружено, просматривается список доступных контрактов сбоя в алфавитном порядке для нахождения совместимого типа. Если совместимые типы имеют два контракта сбоя (например, один является подклассом другого), при десериализации сбоя может быть использован неправильный тип. Это происходит только в случае, если в контракте сбоя не указано имя, пространство имен и действие. Во избежание данной проблемы всегда полностью определяйте контракты сбоя, указывая атрибуты имени, пространства имен и действия. Кроме того, если определено несколько родственных контрактов сбоя, производных от общего базового класса, обязательно помечайте все новые элементы атрибутом `[DataMember(IsRequired=true)]`. Дополнительные сведения об использовании атрибута `IsRequired` см. в разделе <xref:System.Runtime.Serialization.DataMemberAttribute>. В этом случае базовый класс не будет считаться совместимым типом, а сбой будет десериализован в правильный производный тип.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.CommunicationException>  
 <xref:System.ServiceModel.FaultContractAttribute.Action%2A>  
 <xref:System.ServiceModel.FaultException.Code%2A>  
 <xref:System.ServiceModel.FaultException.Reason%2A>  
 <xref:System.ServiceModel.FaultCode.SubCode%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 [Определение и указание сбоев](../../../docs/framework/wcf/defining-and-specifying-faults.md)
