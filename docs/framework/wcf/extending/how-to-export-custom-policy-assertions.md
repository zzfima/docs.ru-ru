---
title: "Как экспортировать утверждения пользовательской политики | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Как экспортировать утверждения пользовательской политики
В утверждениях политики описываются возможности и требования конечной точки службы.Приложения\-службы могут использовать проверочные утверждения пользовательской политики в метаданных службы для передачи конечной точки, привязки или информации о настройке контракта клиентскому приложению.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно использовать для экспорта проверочных утверждений в выражения политики, прикрепленные в привязках WSDL в конечной точке, операции или темах сообщений, в зависимости от передаваемых возможностей или требований.  
  
 Специальные проверочные утверждения политики экспортируются путем реализации интерфейса <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> на <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName> и либо вставки элемента привязки непосредственно в привязку конечной точки службы, либо регистрации элемента привязки в файле конфигурации приложения.Реализация экспорта политики добавляет проверочное утверждение пользовательской политики как экземпляр <xref:System.Xml.XmlElement?displayProperty=fullName> в соответствующую коллекцию <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=fullName> в контексте <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=fullName>, переданный методу <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>.  
  
 Кроме этого, необходимо проверить свойство <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> класса <xref:System.ServiceModel.Description.WsdlExporter> и экспортировать вложенные выражения и политики и атрибуты инфраструктуры политики в соответствующее пространство имен в зависимости от указанной версии политики.  
  
 Импорт проверочных утверждений пользовательской политики см. в <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> и [Как импортировать утверждения пользовательской политики](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md).  
  
### Экспорт проверочных утверждений пользовательской политики  
  
1.  Реализация интерфейса <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> в <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>.В следующем коде показана реализация проверочного утверждения пользовательской политики на уровне привязки.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2.  Элемент привязки вставляется в привязку конечной точки либо программно, либо при помощи файла конфигурации приложения.См. описанные ниже действия.  
  
### Вставка элемента привязки при помощи файла конфигурации приложения  
  
1.  Реализуйте <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=fullName> для элемента привязки проверочного утверждения пользовательской политики.  
  
2.  Добавьте расширение элемента привязки в файл конфигурации с помощью элемента [\<bindingElementExtensions\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md).  
  
3.  Создайте специальную привязку с помощью <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>.  
  
### Вставка элемента привязки программными средствами  
  
1.  Создайте новый элемент <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName> и добавьте его в <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>.  
  
2.  Добавьте пользовательскую привязку, описанную на шаге 1,в новую конечную точку и добавьте эту новую конечную точку службы в <xref:System.ServiceModel.ServiceHost?displayProperty=fullName>, вызвав метод <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
3.  Откройте <xref:System.ServiceModel.ServiceHost>.В следующем коде показан пример создания специальной привязки и вставки элементов привязки программными средствами.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## См. также  
 <xref:System.ServiceModel.Description.IPolicyImportExtension>   
 <xref:System.ServiceModel.Description.IPolicyExportExtension>   
 [Как импортировать утверждения пользовательской политики](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)