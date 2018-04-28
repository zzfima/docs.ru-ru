---
title: Образец асинхронной операции Find
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1545791eceae6d4651ca5299a84623466e8b4976
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="asynchronous-find-sample"></a>Образец асинхронной операции Find
Этот образец показывает, как использовать асинхронную операцию поиска из клиентского приложения.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Преимущества такого конструктивного решения в том, что клиент асинхронно уведомляется о конечных точках, найденных в результате выполнения поискового запроса. Чтобы увидеть, как это происходит, откройте файл Client.cs. Обратите внимание, что объект <xref:System.ServiceModel.Discovery.DiscoveryClient> имеет два делегата, подключенные к обработчикам событий. Один из делегатов вызывается при возникновении события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>, а другой - при каждом возникновении события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>. Образец показывает, как можно использовать этот шаблон в собственном приложении.  
  
> [!NOTE]
>  Образец использует конечные точки HTTP, а для запуска ему понадобятся соответствующие URL ACL. Дополнительные сведения см. в разделе [Настройка протоколов HTTP и HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями. Если команда не работает, следует указать домен и имя пользователя в следующих аргументах. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл AsyncFind.sln.  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Откройте командную строку [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], перейдите в каталог \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug или \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug и запустите файл Service.exe.  
  
4.  После запуска службы перейдите в каталог \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug или WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug и запустите файл Client.exe.  
  
5.  Обратите внимание, что клиент может найти и вызвать службу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a>См. также
