---
title: "Образец асинхронной операции Find | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Образец асинхронной операции Find
Этот образец показывает, как использовать асинхронную операцию поиска из клиентского приложения.  
  
## Подробные сведения об образце  
 Преимущества такого конструктивного решения в том, что клиент асинхронно уведомляется о конечных точках, найденных в результате выполнения поискового запроса.Чтобы увидеть, как это происходит, откройте файл Client.cs.Обратите внимание, что объект <xref:System.ServiceModel.Discovery.DiscoveryClient> имеет два делегата, подключенные к обработчикам событий.Один из делегатов вызывается при возникновении события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>, а другой — при каждом возникновении события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.Образец показывает, как можно использовать этот шаблон в собственном приложении.  
  
> [!NOTE]
>  Образец использует конечные точки HTTP, а для запуска ему понадобятся соответствующие URL ACL.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Настройка HTTP и HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями.Если команда не работает, следует указать домен и имя пользователя в следующих аргументах.`netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### Настройка, построение и выполнение образца  
  
1.  Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл AsyncFind.sln.  
  
2.  Чтобы построить решение, нажмите CTRL\+SHIFT\+B.  
  
3.  Откройте командную строку [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], перейдите в каталог \\WCF\\Basic\\Discovery\\AsyncFind\\CS\\service\\bin\\Debug или \\WCF\\Basic\\Discovery\\AsyncFind\\VB\\service\\bin\\Debug и запустите файл Service.exe.  
  
4.  После запуска службы перейдите в каталог \\WCF\\Basic\\Discovery\\AsyncFind\\CS\\client\\bin\\Debug или WCF\\Basic\\Discovery\\AsyncFind\\VB\\client\\bin\\Debug и запустите файл Client.exe.  
  
5.  Обратите внимание, что клиент может найти и вызвать службу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## См. также