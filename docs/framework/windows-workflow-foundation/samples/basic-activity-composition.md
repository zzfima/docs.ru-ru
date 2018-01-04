---
title: "Сочетание базовых действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 047948552471b33af8690b526db7c416e87f897a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="basic-activity-composition"></a>Сочетание базовых действий
В этом образце показывается создание пользовательских и предоставляемых системой действий для построения других пользовательских действий.  
  
 Рабочий процесс, использующий действие «Survey», планирует действие «Survey» со списком вопросов, а затем выводит полученные ответы.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В данном образце используются три пользовательских действия. `ReadLine`— Это простой <xref:System.Activities.NativeActivity> \<строка >, создающего <xref:System.Activities.Bookmark> по расписанию, а затем устанавливает `Return` <xref:System.Activities.OutArgument%601> для значения, которое <xref:System.Activities.Bookmark> возобновляется. `Prompt`— <xref:System.Activities.Activity%601> \<строка >, принимающий <xref:System.Activities.InArgument%601>< строка\> с именем `Text` и возвращает пользовательский ответ в `Result` <xref:System.Activities.OutArgument%601> \<строки >. Действие `Prompt` использует действия <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.WriteLine>, поставляемые совместно с платформой .NET Framework, а также содержит пользовательское действие `ReadLine` для получения ввода пользователя. Последним пользовательским действием является действие `Survey`. Это <xref:System.Activities.Activity>< ICollection\<строка >>.  Действие принимает <xref:System.Activities.InArgument%601>< IEnumerable < строка\>> с именем `Questions` и заполняет `Result` выходного аргумента с ответами. Действие `Survey` использует действия <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.AddToCollection%601>, поставляемые совместно с платформой .NET Framework, а также использует действие `Prompt` для задания вопросов из опроса и получения ответов.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте **BasicActivityComposition.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`