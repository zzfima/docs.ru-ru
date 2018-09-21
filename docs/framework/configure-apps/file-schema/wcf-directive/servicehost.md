---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 730b1188a95d0e35d7431d43884e867e5520585e
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46517325"
---
# <a name="servicehost"></a>\@ServiceHost
Связывает фабрику, используемую для создания узла службы, с размещаемой службой и другими элементами программирования, необходимыми для доступа или компиляции кода размещения, представленного в SVC-файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a>Атрибуты  
  
#### <a name="service"></a>Служба  
 Имя типа CLR размещенной службы. Это должно быть полное имя типа, который реализует один или несколько контактов службы.  
  
#### <a name="factory"></a>Factory  
 Имя типа CLR фабрики узла службы, используемой для создания узла службы. Этот атрибут является необязательным. Если данный атрибут не задан, по умолчанию используется значение <xref:System.ServiceModel.Activation.ServiceHostFactory>, которое возвращает экземпляр <xref:System.ServiceModel.ServiceHost>.  
  
#### <a name="debug"></a>Отладка  
 Указывает, должны ли службы Windows Communication Foundation (WCF) компилироваться с отладочными символами. `true` Если службы WCF должны компилироваться с отладочными символами. в противном случае `false`.  
  
#### <a name="language"></a>Язык  
 Задает язык, используемый при компиляции всего встроенного кода в файле (SVC). Значения данного атрибута могут представлять любой язык, поддерживаемый .NET, включая C#, VB и JS, что соответствует языкам C#, Visual Basic .NET и JScript .NET. Этот атрибут является необязательным.  
  
#### <a name="codebehind"></a>CodeBehind  
 Определяет файл исходного кода, реализующего веб-службу XML, если реализующий ее класс находится в другом файле и не был скомпилирован в сборку и помещен в каталог «\Bin».  
  
## <a name="remarks"></a>Примечания  
 <xref:System.ServiceModel.ServiceHost> Используется для размещения службы — это точка расширения в модели программирования Windows Communication Foundation (WCF). Для создания узла службы <xref:System.ServiceModel.ServiceHost> используется шаблон фабрики, поскольку он, возможно, имеет полиморфный тип, экземпляр которого среда размещения не должна создавать явно.  
  
 В реализации по умолчанию используется фабрика <xref:System.ServiceModel.Activation.ServiceHostFactory> для создания экземпляра узла службы <xref:System.ServiceModel.ServiceHost>. Но можно предоставить собственную фабрику (один, которая возвращает производный узел), указав имя типа CLR реализации фабрики в [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директива.  
  
 Чтобы использовать собственный настраиваемой фабрики узла службы вместо фабрики по умолчанию, просто предоставить имя типа в [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директива следующим образом:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Создавайте реализацию фабрики в наиболее простом виде. Если имеется значительный объем пользовательской логики, то можно увеличить возможность повторного использования кода, если разместить эту логику на узле, а не в фабрике.  
  
 Например, чтобы включить конечную точку с поддержкой AJAX для `MyService`, укажите <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> значения `Factory` атрибута, а не значение по умолчанию <xref:System.ServiceModel.Activation.ServiceHostFactory>в [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) директив как показано в следующем примере.  
  
## <a name="example"></a>Пример  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>См. также  
 [Пользовательский узел службы](../../../../../docs/framework/wcf/samples/custom-service-host.md)
