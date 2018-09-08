---
title: Использование AsyncOperationContext в образце действия
ms.date: 03/30/2017
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
ms.openlocfilehash: 4358a364a3f7ec69b7c1c548fcf82fe494f37505
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44196911"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`