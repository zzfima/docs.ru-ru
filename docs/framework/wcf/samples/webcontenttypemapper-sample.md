---
title: Пример WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 540e5e775cf7b2a5a5b585d98772415653fa833a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143568"
---
# <a name="webcontenttypemapper-sample"></a>Пример WebContentTypeMapper
В этом примере показано, как сопоставить новые типы содержимого в форматах сообщений Windows Communication Foundation (WCF).  
  
 Элемент <xref:System.ServiceModel.Description.WebHttpEndpoint> подключается к кодеру веб-сообщений, который позволяет WCF получать JSON, XML или необработанные двоичные сообщения в одной и той же точке. Кодировщик определяет формат тела сообщения, просмотрев тип содержимого HTTP запроса. В этом примере показан класс <xref:System.ServiceModel.Channels.WebContentTypeMapper>, который позволяет пользователю управлять сопоставлением типа содержимого и формата тела.  
  
 WCF предоставляет набор карт по умолчанию для типов содержимого. Например, `application/json` сопоставляется с JSON, а `text/xml` сопоставляет с XML. Любой тип содержимого, который не сопоставляется с JSON или XML, сопоставляется с необработанным двоичным форматом.  
  
 В некоторых сценариях (например, интерфейсы API внедрения) разработчик службы не управляет типом содержимого, возвращаемым клиентом. Например, клиенты могут возвращать JSON как `text/javascript`, а не `application/json`. В этом случае разработчик службы должен предоставить тип, унаследованный от <xref:System.ServiceModel.Channels.WebContentTypeMapper>, для правильной обработки данного типа содержимого, как показано в следующем образце кода.  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 Тип должен переопределить метод <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>. Метод должен оценить аргумент `contentType` и возвратить одно из следующих значений: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> или <xref:System.ServiceModel.Channels.WebContentFormat.Default>. Возврат <xref:System.ServiceModel.Channels.WebContentFormat.Default> следует сопоставлениям кодировщика веб-сообщений по умолчанию. В предыдущем примере кода тип содержимого `text/javascript` сопоставляется с JSON, а все другие сопоставления остаются неизменными.  
  
 Для использования класса `JsonContentTypeMapper` воспользуйтесь следующими элементами Web.config:  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Чтобы проверить требование к использованию JsonContentTypeMapper, удалите атрибут contentTypeMapper из указанного выше файла конфигурации. Не удается загрузить страницу клиента при попытке использования `text/javascript` для отправки содержимого JSON.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Создайте решение WebContentTypeMapperSample.sln, как описано в [создании образцов Фонда коммуникации Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
3. Перейдите `http://localhost/ServiceModelSamples/JCTMClientPage.htm` к (не открывайте JCTMClientPage.htm в браузере из каталога проекта).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
