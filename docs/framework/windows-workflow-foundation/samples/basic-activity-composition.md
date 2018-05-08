---
title: Сочетание базовых действий
ms.date: 03/30/2017
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
ms.openlocfilehash: 67cdad30c60ebbeaf546d7086c6e895fa49a51c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="basic-activity-composition"></a>Сочетание базовых действий
В этом образце показывается создание пользовательских и предоставляемых системой действий для построения других пользовательских действий.  
  
 Рабочий процесс, использующий действие «Survey», планирует действие «Survey» со списком вопросов, а затем выводит полученные ответы.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В данном образце используются три пользовательских действия. `ReadLine` — Это простой <xref:System.Activities.NativeActivity> \<строка >, создающего <xref:System.Activities.Bookmark> по расписанию, а затем устанавливает `Return` <xref:System.Activities.OutArgument%601> для значения, которое <xref:System.Activities.Bookmark> возобновляется. `Prompt` — <xref:System.Activities.Activity%601> \<строка >, принимающий <xref:System.Activities.InArgument%601>< строка\> с именем `Text` и возвращает пользовательский ответ в `Result` <xref:System.Activities.OutArgument%601> \<строки >. Действие `Prompt` использует действия <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.WriteLine>, поставляемые совместно с платформой .NET Framework, а также содержит пользовательское действие `ReadLine` для получения ввода пользователя. Последним пользовательским действием является действие `Survey`. Это <xref:System.Activities.Activity>< ICollection\<строка >>.  Действие принимает <xref:System.Activities.InArgument%601>< IEnumerable < строка\>> с именем `Questions` и заполняет `Result` выходного аргумента с ответами. Действие `Survey` использует действия <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.AddToCollection%601>, поставляемые совместно с платформой .NET Framework, а также использует действие `Prompt` для задания вопросов из опроса и получения ответов.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте **BasicActivityComposition.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`