---
title: Привязки Windows Communication Foundation
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
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 926cdab8b835aa170fc0cdc0046c3fef579c3fec
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="windows-communcation-foundation-bindings"></a>Привязки Windows Communication Foundation
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] способ реализации приложения отделяется от способа его взаимодействия с другим программным обеспечением. Привязки используются для указания транспорта, кодировки и данных протокола, требуемых для связи клиентов и служб. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] привязки используются для создания базового описания конечной точки, поэтому большинство данных о привязке должно быть согласовано сторонами, обменивающимися информацией. Самым простым способом является использование клиентами службы той же привязки, которую использует конечная точка службы. Дополнительные сведения о том, как это сделать см. в разделе [с помощью привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb).  
  
 Привязка состоит из коллекции элементов привязки. Каждый элемент описывает некоторый аспект взаимодействия конечной точки с клиентами. Привязка должна содержать как минимум один элемент транспорта, как минимум один элемент кодирования сообщений (по умолчанию предоставляемый элементом транспорта привязки) и любое количество других элементов протоколов привязки. Процесс, создающий среду выполнения из этого описания, позволяет добавлять код из каждого элемента привязки в эту среду выполнения.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрены привязки, содержащие стандартные наборы элементов привязки. Можно использовать их с параметрами по умолчанию либо изменить значения этих параметров согласно потребностям пользователя. Эти предоставляемые системой привязки имеют свойства, обеспечивающие прямое управление элементами привязки и их параметрами. Также можно параллельно работать с несколькими версиями привязки, присвоив отдельное имя каждой из них. Дополнительные сведения см. в разделе [Configuring System-Provided привязки](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).  
  
 Если потребуется коллекция элементов привязки, не предусмотренная в числе предоставляемых системой, можно создать пользовательскую привязку, содержащую требуемую коллекцию элементов привязки. Создавать эти пользовательские привязки очень просто, и для этого не требуется новый класс, однако в них отсутствуют свойства для управления элементами привязки или их параметрами. Обращаться к элементам привязки и изменять их параметры можно через содержащую их коллекцию. Дополнительные сведения см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Настройка привязок, предоставляемых системой](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 Описание способов использования и изменения привязок, предусмотренных в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], для поддержки стандартных сценариев.  
  
 [Использование привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 Описание способов определения привязок [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для служб и клиентов (принудительно в коде или декларативно с помощью конфигурации).  
  
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 Описание элемента <xref:System.ServiceModel.Channels.CustomBinding> и сферы его применения.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
