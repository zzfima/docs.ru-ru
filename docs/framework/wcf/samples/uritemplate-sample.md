---
title: "Образец UriTemplate | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Образец UriTemplate
Класс <xref:System.UriTemplate> предоставляет методы для работы с наборами кодов URI, использующих общую структуру.Данный образец демонстрирует следующие ключевые понятия, связанные с `UriTemplate`.  
  
-   Синтаксис создания шаблонов.  
  
-   Создание экземпляров кодов URI из шаблона `UriTemplate` с помощью методов <xref:System.UriTemplate.BindByName%2A> и <xref:System.UriTemplate.BindByPosition%2A>.  
  
-   Метод <xref:System.UriTemplateTable.Match%2A>, являющийся обратной операцией для `BindByName` и `BindByPosition`.  
  
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
>  `<Диск_установки>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## См. также  
 [Таблица UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)   
 [Диспетчер таблицы UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)