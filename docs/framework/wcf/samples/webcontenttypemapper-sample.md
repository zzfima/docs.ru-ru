---
title: "Образец WebContentTypeMapper | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Образец WebContentTypeMapper
В этом образце показано, как сопоставить новые типы содержимого с форматами текста сообщения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 Элемент <xref:System.ServiceModel.Description.WebHttpEndpoint> подключает кодировщик веб\-сообщений, который позволяет [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] получать сообщения JSON, XML или необработанные двоичные сообщения в одной и той же конечной точке.Кодировщик определяет формат тела сообщения, просмотрев тип содержимого HTTP запроса.В этом образце показан класс <xref:System.ServiceModel.Channels.WebContentTypeMapper>, который позволяет пользователю управлять сопоставлением типа содержимого и формата тела.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет набор сопоставлений по умолчанию для типов содержимого.Например, `application/json` сопоставляется с JSON, а `text/xml` сопоставляет с XML.Любой тип содержимого, который не сопоставляется с JSON или XML, сопоставляется с необработанным двоичным форматом.  
  
 В некоторых сценариях \(например, интерфейсы API внедрения\) разработчик службы не управляет типом содержимого, возвращаемым клиентом.Например, клиенты могут возвращать JSON как `text/javascript`, а не `application/json`.В этом случае разработчик службы должен предоставить тип, унаследованный от <xref:System.ServiceModel.Channels.WebContentTypeMapper>, для правильной обработки данного типа содержимого, как показано в следующем образце кода.  
  
```  
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
  
 Тип должен переопределить метод <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>.Метод должен оценить аргумент `contentType` и возвратить одно из следующих значений: <xref:System.ServiceModel.Channels.WebContentFormat>, <xref:System.ServiceModel.Channels.WebContentFormat>, <xref:System.ServiceModel.Channels.WebContentFormat> или <xref:System.ServiceModel.Channels.WebContentFormat>.Возврат <xref:System.ServiceModel.Channels.WebContentFormat> следует сопоставлениям кодировщика веб\-сообщений по умолчанию.В предыдущем образце кода тип содержимого `text/javascript` сопоставляется с JSON, а все другие сопоставления остаются неизменными.  
  
 Для использования класса `JsonContentTypeMapper` воспользуйтесь следующими элементами Web.config:  
  
```  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Чтобы проверить требование к использованию JsonContentTypeMapper, удалите атрибут contentTypeMapper из указанного выше файла конфигурации.Не удается загрузить страницу клиента при попытке использования `text/javascript` для отправки содержимого JSON.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Выполните построение решения WebContentTypeMapperSample.sln, описанное в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к странице http:\/\/localhost\/ServiceModelSamples\/JCTMClientPage.htm \(не открывайте страницу JCTMClientPage.htm в браузере из каталога проекта\).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
  
## См. также