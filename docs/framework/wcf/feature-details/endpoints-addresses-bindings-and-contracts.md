---
title: 'Конечные точки: адреса, привязки и контракты'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- endpoints [WCF]
- Windows Communication Foundation [WCF], endpoints
- WCF [WCF], endpoints
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 477c23facd846580bac698ce6e61d02e11afe430
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="endpoints-addresses-bindings-and-contracts"></a>Конечные точки: адреса, привязки и контракты
Вся связь со [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] службы осуществляется с помощью *конечные точки* службы. Конечные точки обеспечивают доступ клиентов к функциональным возможностям службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Каждая конечная точка состоит из четырех свойств:  
  
-   адрес, показывающий, где можно найти конечную точку;  
  
-   привязку, показывающую, как клиент может связаться с конечной точкой;  
  
-   контракт, определяющий доступные операции;  
  
-   набор поведений, задающих сведения о локальной реализации конечной точки.  
  
 В настоящем разделе описана структура конечной точки и объясняется, каким образом она представлена в объектной модели [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="the-structure-of-an-endpoint"></a>Структура конечной точки  
 Каждая конечная точка состоит из следующего.  
  
-   Адрес: адрес однозначно определяет конечную точку и указывает потенциальным потребителям на место расположения службы. В объектной модели [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] адрес представлен классом <xref:System.ServiceModel.EndpointAddress>. Класс <xref:System.ServiceModel.EndpointAddress> содержит следующее.  
  
    -   Свойство <xref:System.ServiceModel.EndpointAddress.Uri%2A>, представляющее адрес службы.  
  
    -   Свойство <xref:System.ServiceModel.EndpointAddress.Identity%2A>, представляющее удостоверение безопасности службы и коллекцию необязательных заголовков сообщений. Необязательные заголовки сообщений используются для вывода дополнительной и более подробной информации, необходимой для идентификации конечной точки или взаимодействия с ней.  
  
     Дополнительные сведения см. в разделе [Задание адреса конечной точки](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   Привязка. Привязка задает способ связи клиента с конечной точкой. В том числе следующее:  
  
    -   используемый транспортный протокол (например, TCP или HTTP);  
  
    -   используемую в сообщениях кодировку (например, текст или двоичное кодирование);  
  
    -   необходимые требования безопасности (например, безопасность сообщений SSL или SOAP).  
  
     Дополнительные сведения см. в разделе [Общие сведения о привязках WCF](../../../../docs/framework/wcf/bindings-overview.md). Привязка в объектной модели [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] представлена абстрактным базовым классом <xref:System.ServiceModel.Channels.Binding>. В большинстве сценариев пользователи могут использовать только одну из предусмотренных системой привязок. Дополнительные сведения см. в разделе [привязка, предоставляемая системой](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
-   Контракты. Контракты показывают, какие функциональные возможности дает клиенту конечная точка. В контракте задается следующее:  
  
    -   операции, которые могут быть вызваны клиентом;  
  
    -   форма сообщения;  
  
    -   тип входных параметров или данных, требуемых для вызова операции;  
  
    -   тип обработки или ответного сообщения, который может ожидать клиент.  
  
     Дополнительные сведения об определении контракта см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
-   Поведения. Поведения конечной точки можно использовать для настройки локального поведения конечной точки службы. Поведения конечной точки выполняют это путем участия в процессе создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]среды выполнения. Примером поведения является свойство <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A>, позволяющее указывать отличный от адреса SOAP или WSDL адрес прослушивания. Дополнительные сведения см. в разделе [ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## <a name="defining-endpoints"></a>Определение конечных точек  
 Адрес конечной точки службы можно задать императивно с помощью кода или декларативно с помощью конфигурации. Дополнительные сведения см. в разделе [как: создать конечную точку службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) и [как: создать конечную точку службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 В данном разделе объясняется назначение привязок, конечных точек и адресов; показано, как конфигурировать привязку и конечную точку, и демонстрируется, как использовать поведение `ClientVia` и свойство `ListenUri`.  
  
 [Адреса](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 Описывается, как выполняется обращение к конечным точкам в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)  
 Описывается, как привязки используются для указания транспорта, кодировки и данных протокола, требуемых для связи клиентов и служб.  
  
 [Контракты](../../../../docs/framework/wcf/feature-details/contracts.md)  
 Описывается, как контакты определяют методы службы.  
  
 [Практическое руководство. Создание конечной точки службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Описывается, как создать конечную точку службы в конфигурации.  
  
 [Практическое руководство. Создание конечной точки службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Описывается, как создать конечную точку службы в коде.  
  
 [Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 Описывает, как для обнаружения ошибок в реализациях службы и конфигурации без размещения службы с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="see-also"></a>См. также  
 [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
