---
title: Сочетание базовых действий
ms.date: 03/30/2017
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
ms.openlocfilehash: ade8187ca44a8182b55cf0f01e5bfe5a9a747255
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518380"
---
# <a name="basic-activity-composition"></a>Сочетание базовых действий
В этом образце показывается создание пользовательских и предоставляемых системой действий для построения других пользовательских действий.  
  
 Рабочий процесс, использующий действие «Survey», планирует действие «Survey» со списком вопросов, а затем выводит полученные ответы.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В данном образце используются три пользовательских действия. `ReadLine` — Это простой <xref:System.Activities.NativeActivity> \<строка >, создающий <xref:System.Activities.Bookmark> по расписанию, а затем задает `Return` <xref:System.Activities.OutArgument%601> для значения, с которого <xref:System.Activities.Bookmark> возобновляется. `Prompt` — <xref:System.Activities.Activity%601> \<строка >, принимающий <xref:System.Activities.InArgument%601>< строка\> с именем `Text` и возвращает пользовательский ответ в `Result` <xref:System.Activities.OutArgument%601> \<строки >. Действие `Prompt` использует действия <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.WriteLine>, поставляемые совместно с платформой .NET Framework, а также содержит пользовательское действие `ReadLine` для получения ввода пользователя. Последним пользовательским действием является действие `Survey`. Это <xref:System.Activities.Activity>< ICollection\<строка >>.  Действие принимает <xref:System.Activities.InArgument%601>< IEnumerable < строка\>> с именем `Questions` и заполняет `Result` выходной аргумент ответы. Действие `Survey` использует действия <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.AddToCollection%601>, поставляемые совместно с платформой .NET Framework, а также использует действие `Prompt` для задания вопросов из опроса и получения ответов.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте **BasicActivityComposition.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`