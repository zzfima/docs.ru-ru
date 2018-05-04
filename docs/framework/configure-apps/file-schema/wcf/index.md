---
title: Схем конфигурации WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 147df2200017224bd20ad7eaca283f4dbcd08fb2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="wcf-configuration-schema"></a>Схем конфигурации WCF
Элементы конфигурации Windows Communication Foundation (WCF) позволяют настраивать [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] служб и клиентских приложений. [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) можно использовать для создания и изменения файлов конфигурации для клиентов и служб. Поскольку файлы конфигурации имеют формат XML, для их изменения вручную с помощью текстового редактора необходимо уметь работать с XML-кодом. В противном случае возможно возникновение проблем, таких как отсутствие тега или атрибута элемента XML. Это обусловлено тем, что в тегах и атрибутах элементов XML учитывается регистр символов.  
  
 Система конфигурации [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] основана на пространстве имен <xref:System.Configuration>. Поэтому можно использовать все стандартные функции, имеющиеся в пространстве имен <xref:System.Configuration>, например блокировку, шифрование и объединение конфигурации для повышения безопасности приложения и его конфигурации. Дополнительные сведения об этих возможностях см. в следующих разделах:  
  
 [Шифрование данных конфигурации](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [Блокировка параметров конфигурации](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 В этом разделе описаны все возможные значения каждого элемента конфигурации и их взаимодействие с другими элементами конфигурации WCF. На следующей иллюстрации показана схема конфигурации WCF.  
  
 ![Схема конфигурации WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  Необходимо защищать разделы конфигурации [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в файлах конфигурации приложения (app.config) с помощью соответствующих списков управления доступом (ACL), чтобы предотвратить потенциальные угрозы безопасности.  Например, необходимо гарантировать, что иметь доступ или изменять параметры безопасности в привязках приложения или разделе модели службы в файле конфигурации для службы смогут только определенные лица.  
  
## <a name="in-this-section"></a>В этом разделе  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 Приводится описание элемента `ServiceModel`.  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 Настраивает средство SMSvcHost.exe.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 Элемент верхнего уровня для установки параметров при использовании сериализаторов, таких как <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Настройка приложений Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 Описывает настройку служб и клиентов [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].
