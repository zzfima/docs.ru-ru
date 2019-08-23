---
title: Импорт пользовательских метаданных для расширения WCF
ms.date: 03/30/2017
ms.assetid: 78beb28f-408a-4c75-9c3c-caefe9595b1a
ms.openlocfilehash: 36bc4c9291b60ae5ad6e9964c361ed9e7a7c8317
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963500"
---
# <a name="importing-custom-metadata-for-a-wcf-extension"></a>Импорт пользовательских метаданных для расширения WCF
В Windows Communication Foundation (WCF) импорт метаданных — это процесс создания абстрактного представления службы или ее компонентов из метаданных. Например, WCF может импортировать <xref:System.ServiceModel.Description.ServiceEndpoint> экземпляры, <xref:System.ServiceModel.Channels.Binding> экземпляры или <xref:System.ServiceModel.Description.ContractDescription> экземпляры из документа WSDL для службы. Чтобы импортировать метаданные службы в WCF, используйте реализацию <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> абстрактного класса. Типы, производные от <xref:System.ServiceModel.Description.MetadataImporter> класса, реализуют поддержку импорта форматов метаданных, которые используют преимущества логики импорта WS-Policy в WCF.  
  
 Пользовательские метаданные состоят из элементов XML, которые не могут быть импортированы с помощью средств импорта метаданных, предоставляемых системой. Как правило, они включают пользовательские расширения WSDL и утверждения политики.  
  
 В этом разделе описано, как импортировать пользовательские расширения WSDL и утверждения политики. В нем не рассматривается сам процесс импорта. Дополнительные сведения об использовании типов, которые экспортируют и импортируют метаданные независимо от того, поддерживаются ли эти метаданные как настраиваемые или поддерживаемые системой, см. в разделе [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Обзор  
 Тип является реализацией <xref:System.ServiceModel.Description.MetadataImporter> абстрактного класса, входящего в состав WCF. <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> Тип <xref:System.ServiceModel.Description.WsdlImporter> импортирует метаданные языка WSDL с прикрепленными политиками, объединенными в объекте <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType>. Утверждения политики и расширения WSDL, не распознаваемые стандартными средствами импорта метаданных, передаются для импорта зарегистрированным средствам импорта пользовательской политики и WSDL. Как правило, средства импорта реализуются с целью поддержки пользовательских элементов привязки или изменения импортированного контракта.  
  
 В данном разделе рассматриваются следующие вопросы.  
  
1. Реализация и использование интерфейса <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>, который предоставляет данные WSDL пользовательским средствам импорта до создания описаний и создания кода. Этот интерфейс можно использовать для проверки или изменения типов описаний и компиляции кода с использованием заданного набора метаданных.  
  
2. Реализация и использование интерфейса <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>, который предоставляет утверждения политики средствам импорта до создания объектов описания. Этот интерфейс можно использовать для проверки или изменения привязки или контракта на основании загруженных политик.  
  
 Дополнительные сведения об экспорте пользовательских WSDL и утверждений политик см. [в разделе Экспорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="importing-custom-wsdl-extensions"></a>Импорт пользовательских расширений WSDL  
 Чтобы добавить поддержку импорта расширений WSDL, следует реализовать интерфейс <xref:System.ServiceModel.Description.IWsdlImportExtension>, а затем добавить эту реализацию в свойство <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A>. Также <xref:System.ServiceModel.Description.WsdlImporter> может загружать реализации интерфейса <xref:System.ServiceModel.Description.IWsdlImportExtension>, зарегистрированного в файле конфигурации приложения. Обратите внимание, что регистрируется большое количество средств импорта WSDL, при этом имеет значение порядок зарегистрированных средств импорта WSDL.  
  
 Если объект <xref:System.ServiceModel.Description.WsdlImporter> загружает и использует пользовательское средство импорта WSDL, сначала вызывается метод <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%2A>, чтобы разрешить изменение метаданных до начала процесса импорта. Затем выполняется импорт контрактов, после чего вызывается метод <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%2A>, чтобы разрешить изменение контрактов, импортированных из метаданных. И, наконец, вызывается метод <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%2A>, чтобы разрешить изменение импортированных конечных точек.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Импорт пользовательского WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)-документа.  
  
### <a name="importing-custom-policy-assertions"></a>Импорт утверждений пользовательской политики  
 Тип и [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) автоматически обрабатывают обработку различных типов утверждений политики в выражениях политик, прикрепленных к документам WSDL. <xref:System.ServiceModel.Description.WsdlImporter> Эти средства собирают, нормализуют и объединяют выражения политики, прикрепленные к привязкам WSDL и портам WSDL.  
  
 Чтобы добавить поддержку утверждений пользовательской политики, следует реализовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension>, а затем добавить эту реализацию в свойство <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>. Также <xref:System.ServiceModel.Description.MetadataImporter> может загружать реализации интерфейса <xref:System.ServiceModel.Description.IPolicyImportExtension>, зарегистрированного в файле конфигурации приложения. Обратите внимание, что регистрируется большое количество средств политик, при этом имеет значение порядок зарегистрированных средств импорта политик.  
  
 Система метаданных многократно вызывает метод <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> для всех зарегистрированных расширений импорта политики для каждой комбинации альтернативной политики, прикрепленной к сообщению, операции и субъекта политики конечной точки. При импорте порта WSDL политики, прикрепленные к порту и соответствующей привязке WSDL, объединяются перед вызовом расширений импорта политики. Доступ к альтернативным политикам осуществляется с помощью <xref:System.ServiceModel.Description.PolicyConversionContext> в виде объектов <xref:System.ServiceModel.Description.PolicyAssertionCollection>. Каждый объект <xref:System.ServiceModel.Description.PolicyAssertionCollection> является коллекцией утверждений политики, представленных объектами <xref:System.Xml.XmlElement>.  
  
 Свойства <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A> и <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A> объекта <xref:System.ServiceModel.Description.PolicyConversionContext> предоставляют объекты <xref:System.ServiceModel.Description.ContractDescription> и <xref:System.ServiceModel.Channels.BindingElement>, импортированные из WSDL. Расширения импорта политики обрабатывают утверждения политики путем поиска экземпляров определенного типа утверждения политики, внесения соответствующих изменений в объекты <xref:System.ServiceModel.Description.ContractDescription> или <xref:System.ServiceModel.Channels.BindingElement> и последующего удаления утверждений политики из соответствующего экземпляра <xref:System.ServiceModel.Description.PolicyAssertionCollection>.  
  
 Атрибут `wsp:Optional` и вложенные выражения политики не нормализуются, поэтому обработка этих конструкций политики выполняется с помощью расширений импорта политики. Кроме того, возможен неоднократный вызов расширений импорта политики с одними и теми же объектами <xref:System.ServiceModel.Description.ContractDescription> и <xref:System.ServiceModel.Channels.BindingElement>, поэтому расширения импорта политики должны быть надежными в такой ситуации.  
  
> [!IMPORTANT]
> В средство импорта могут быть переданы недопустимые или неправильные метаданные. Убедитесь в том, что пользовательские средства импорта являются надежными для всех форм XML.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Импорт пользовательского WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
- [Практическое руководство. Импорт утверждений пользовательской политики](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)
- [Практическое руководство. Создание расширения для ServiceContractGenerator](../../../../docs/framework/wcf/extending/how-to-write-an-extension-for-the-servicecontractgenerator.md)
