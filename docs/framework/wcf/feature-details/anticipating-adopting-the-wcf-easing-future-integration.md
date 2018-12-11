---
title: 'Планирование перехода на платформу Windows Communication Foundation: Упрощение будущей интеграции'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f4cc450b04fd05d390a1f41f3d14c19f4b23be29
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155149"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Планирование перехода на платформу Windows Communication Foundation: Упрощение будущей интеграции
Если вы используете ASP.NET уже сегодня и ожидается в будущем с помощью WCF, этот раздел содержит рекомендации, чтобы убедиться, что новый веб-служб ASP.NET будет работать хорошо вместе с приложениями WCF.  
  
## <a name="general-recommendations"></a>Основные рекомендации  
 Используйте для создания новых служб ASP.NET 2.0. Это обеспечит доступ к усовершенствованиям, появившимся в новой версии. Тем не менее она даст возможность использования компонентов ASP.NET 2.0 вместе с компонентов WCF в одном приложении.  
  
## <a name="protocols"></a>Протоколы  
 Используйте новую функцию ASP.NET 2.0 для проверки соответствия спецификации WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Веб-службы ASP.NET, соответствующие спецификации WS-I Basic Profile 1.1, будут способны взаимодействовать с клиентами WCF с помощью WCF предопределенные привязки, <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Разработка служб  
 Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP вместо заголовка HTTP SOAPAction. WCF использует заголовок SOAPAction HTTP для маршрутизации сообщений.  
  
## <a name="data-representation"></a>Представление данных  
 XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом. При задании типа данных для использования с веб-служб ASP.NET в ближайшем будущем внедрения WCF в будущем, сделайте следующее:  
  
1.  Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
2.  Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа. Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
 Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи. Типы, используемые в сообщениях веб-службами ASP.NET будут иметь возможность обрабатывать как контракты данных в случае приложений WCF, что, помимо прочих преимуществ, повышения производительности в приложениях WCF.  
  
## <a name="security"></a>Безопасность  
 Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS. Клиенты WCF не поддерживают их. Если службу необходимо защитить, используйте параметры, предоставляемые WCF, так как эти параметры обеспечивают больше возможностей и основаны на стандартных протоколах.  
  
## <a name="see-also"></a>См. также  
 [Планирование перехода на платформу Windows Communication Foundation: Упрощение будущей миграции](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
