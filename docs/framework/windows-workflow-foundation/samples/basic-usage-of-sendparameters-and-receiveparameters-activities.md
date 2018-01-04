---
title: "Основное использование действий SendParameters и ReceiveParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 375168f45ee0bba5df1ca723398d448ead89555c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Основное использование действий SendParameters и ReceiveParameters
В этом образце показано использование действий <xref:System.ServiceModel.Activities.SendParametersContent> и <xref:System.ServiceModel.Activities.ReceiveParametersContent>. Служба предоставляет одну операцию, которая принимает строковый аргумент и возвращает его клиенту. В образце показано, как установить параметры для этих действий обмена сообщениями.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Использование этого образца  
  
1.  Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.  
  
2.  Сначала запустите приложение EchoWorkflowService, сформированное в [основной каталог решения]\EchoWorkflowService\bin\debug.  
  
3.  Затем запустите приложение EchoWorkflowClient, сформированное в [основной каталог решения]\EchoWorkflowClient\bin\debug.  
  
4.  Клиент вызывает операцию Echo на службе и печатает результаты. После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.