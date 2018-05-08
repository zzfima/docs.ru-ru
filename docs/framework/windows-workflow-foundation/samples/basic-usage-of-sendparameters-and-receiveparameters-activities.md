---
title: Основное использование действий SendParameters и ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: 8732b10f3f96ccf9ed352f9b54c60a4ee0d1664c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Основное использование действий SendParameters и ReceiveParameters
В этом образце показано использование действий <xref:System.ServiceModel.Activities.SendParametersContent> и <xref:System.ServiceModel.Activities.ReceiveParametersContent>. Служба предоставляет одну операцию, которая принимает строковый аргумент и возвращает его клиенту. В образце показано, как установить параметры для этих действий обмена сообщениями.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Использование этого образца  
  
1.  Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.  
  
2.  Сначала запустите приложение EchoWorkflowService, сформированное в [основной каталог решения]\EchoWorkflowService\bin\debug.  
  
3.  Затем запустите приложение EchoWorkflowClient, сформированное в [основной каталог решения]\EchoWorkflowClient\bin\debug.  
  
4.  Клиент вызывает операцию Echo на службе и печатает результаты. После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.