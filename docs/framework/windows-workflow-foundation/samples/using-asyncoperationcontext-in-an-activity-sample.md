---
title: "Использование AsyncOperationContext в образце действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa2a68bccb4daff380b8de7368c6709c41c5799a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a>Использование AsyncOperationContext в образце действия
В этом образце показано, как разработать настраиваемое действие <xref:System.Activities.CodeActivity>, которое использует <xref:System.Activities.AsyncCodeActivityContext> для асинхронного выполнения работы вне рабочего процесса.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В данном образце действия используются методы <xref:System.IO.FileStream.BeginWrite%2A> и <xref:System.IO.FileStream.EndWrite%2A> в классе <xref:System.IO.FileStream> для асинхронной записи данных в файл. Предлагаемый здесь шаблон может быть адаптирован для использования с другими асинхронными методами. Во время выполнения асинхронной операции могут выполняться другие действия рабочего процесса, но сам рабочий процесс не может быть сохранен.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте образец решения Async.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`  
  
## <a name="see-also"></a>См. также
