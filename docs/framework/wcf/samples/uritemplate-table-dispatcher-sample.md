---
title: "Образец диспетчера таблицы UriTemplate | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Образец диспетчера таблицы UriTemplate
Класс <xref:System.UriTemplateTable> предоставляет структуру ассоциативной таблицы, подобную словарю, для работы с набором экземпляров <xref:System.UriTemplate>.В этом образце показан базовый механизм диспетчеризации, построенный с использованием класса `UriTemplateTable`, стандартный сценарий использования класса `UriTemplateTable`.  
  
 Данный образец демонстрирует следующие ключевые понятия, связанные с классом `UriTemplateTable`:  
  
-   Связывание делегатов с `UriTemplates` в `UriTemplateTable`.  
  
-   Получение правильного делегата обработчика для заданного универсального кода ресурса \(URI\) с помощью метода <xref:System.UriTemplateTable.MatchSingle%2A>.  
  
-   Вызов делегата обработчика для обработки запроса.  
  
### Настройка, построение и выполнение образца  
  
1.  Чтобы создать версию решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## См. также  
 [Таблица UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)   
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)