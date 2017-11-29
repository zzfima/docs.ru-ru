---
title: "Образец обнаружения рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f778fead0e09be36ca2a829dde9cf906f4fcaa9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-discovery-sample"></a>Образец обнаружения рабочего процесса
В этом образце показано, как сделать службу рабочего процесса обнаруживаемой, а также как создать настраиваемое действие кода, используемое для поиска определенной службы.  
  
## <a name="demonstrates"></a>Демонстрации  
 Действия по обнаружению и использование рабочего процесса  
  
## <a name="discussion"></a>Обсуждение  
 В первой части образца служба рабочего процесса делается доступной для обнаружения с помощью конфигурации. Конфигурацию можно также использовать для правильного применения службы с настраиваемыми метаданными (такими как области). На клиенте в образце используется настраиваемое действие кода, которое при помощи обнаружения осуществляет поиск службы, соответствующей конкретному контракту. Действие кода выводит URI, в дальнейшем используемый действием отправки.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Этот образец использует конечные точки HTTP, который должен иметь соответствующие списки управления доступом URL-адрес для запуска (см. [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения). Нужные списки управления доступом будут добавлены после выполнения следующей команды в командной строке с повышенными привилегиями. Если оболочка не распознает формат переменной, замените домен и имя пользователя в следующих аргументах.  
  
     **добавить urlacl url-адрес Netsh http = http: / / +: 8000 / пользователь = % DOMAIN %\\% UserName %**  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
