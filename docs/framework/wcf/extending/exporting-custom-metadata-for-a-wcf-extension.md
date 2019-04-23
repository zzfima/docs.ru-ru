---
title: Экспорт пользовательских метаданных для расширения WCF
ms.date: 03/30/2017
ms.assetid: 53c93882-f8ba-4192-965b-787b5e3f09c0
ms.openlocfilehash: 5134b57c59268b139239021bc2b4f6f4538ad27d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334514"
---
# <a name="exporting-custom-metadata-for-a-wcf-extension"></a>Экспорт пользовательских метаданных для расширения WCF
В Windows Communication Foundation (WCF), экспорта метаданных — это процесс описания конечных точек службы и проецирования их в параллельное, стандартизованное представление, клиенты могут использовать, чтобы понять, как использовать службу. Пользовательские метаданные состоят из элементов XML, которые не могут быть экспортированы с помощью средств экспорта метаданных, предоставляемых системой. Обычно сюда входят пользовательские элементы WSDL для определенных пользователем поведений, элементов привязки и утверждений политики о возможностях и требованиях привязок и контрактов.  
  
 В этом разделе описано, как экспортировать пользовательские элементы WSDL и утверждения политики, но при этом не рассматривается сам процесс экспорта. Дополнительные сведения о том, как использовать типы, которые экспортируют и импортируют метаданные независимо от того, являются ли они пользовательскими или созданными системой, см. в разделе [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Обзор  
 При публикации метаданных с помощью <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> исследуется и XSD и WSDL--включая утверждения политики--создаются для всех контрактов и привязок, поддерживаемых WCF с помощью предоставляемых системой атрибутов и привязок. Однако для правильного экспорта пользовательских атрибутов поведения или элементов привязки требуется их поддержка.  
  
 В данном разделе рассматриваются следующие вопросы.  
  
1. Реализация и использование интерфейса <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType>, который предоставляет данные создания WSDL перед публикацией WSDL.  
  
2. Реализация и использование интерфейса <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>, который предоставляет данные политики для экспорта утверждений политики в данные WSDL.  
  
 Дополнительные сведения об импорте пользовательского языка WSDL и утверждений политики см. в разделе [Импорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-custom-wsdl-elements"></a>Экспорт пользовательских элементов WSDL  
 Реализуйте <xref:System.ServiceModel.Description.IWsdlExportExtension> в поведении операции, поведении контракта, поведении конечной точки или элементе привязки (<xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior>, <xref:System.ServiceModel.Description.IEndpointBehavior> или <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> соответственно) и вставьте эти поведения или элементы привязки в описание службы, которую требуется экспортировать. (Дополнительные сведения о вставке поведений см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)). Для каждой конечной точки вызывается метод <xref:System.ServiceModel.Description.IWsdlExportExtension>, и каждая конечная точка сначала экспортирует контракт, если он еще не был экспортирован. Можно принять участие в любом процессе экспорта, в зависимости от потребностей:  
  
-   Используйте <xref:System.ServiceModel.Description.WsdlContractConversionContext> для изменения экспортированных метаданных в методе <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A>.  
  
-   Используйте <xref:System.ServiceModel.Description.WsdlEndpointConversionContext> для изменения экспортированных метаданных для конечной точки в методе <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A>.  
  
 Метод <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> вызывается для всех реализаций <xref:System.ServiceModel.Description.IWsdlExportExtension> в экспортируемом экземпляре <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>.  Метод <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> вызывается для всех реализаций <xref:System.ServiceModel.Description.IWsdlExportExtension> с экспортируемым экземпляром <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>.  
  
 Дополнительные сведения см. в разделе [Как Экспорт WSDL пользовательских](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md) образец [публикация WSDL пользовательских](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md).  
  
## <a name="exporting-custom-policy-assertions"></a>Экспорт утверждений пользовательской политики  
 Реализуйте <xref:System.ServiceModel.Description.IPolicyExportExtension> в <xref:System.ServiceModel.Channels.BindingElement> и добавьте в привязку этот элемент привязки, чтобы записать в WSDL утверждения пользовательской политики о поддержке привязки и возможностях контракта. Метод <xref:System.ServiceModel.Description.IPolicyExportExtension> вызывается один раз при экспорте реализованного элемента привязки в привязке и передает <xref:System.ServiceModel.Description.PolicyConversionContext> в метод <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>. Эти методы можно использовать для экземпляра <xref:System.ServiceModel.Description.PolicyConversionContext>, чтобы добавить утверждения политики, присоединенные к привязке WSDL в субъектах сообщения, операции или конечной точки.  
  
 Дополнительные сведения см. в разделе [Как Экспорт утверждений пользовательской политики](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md).  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Экспорт пользовательского языка WSDL](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)
- [Практическое руководство. Экспорт утверждений пользовательской политики](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md)
- [Импорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)
