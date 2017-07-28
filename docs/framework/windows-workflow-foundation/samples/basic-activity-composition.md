---
title: "Сочетание базовых действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Сочетание базовых действий
В этом образце показывается создание пользовательских и предоставляемых системой действий для построения других пользовательских действий.  
  
 Рабочий процесс, использующий действие «Survey», планирует действие «Survey» со списком вопросов, а затем выводит полученные ответы.  
  
## Подробные сведения об образце  
 В данном образце используются три пользовательских действия.`ReadLine` является простым <xref:System.Activities.NativeActivity>\<string\>, который создает <xref:System.Activities.Bookmark> по расписанию, а затем задает значение свойства `Return`<xref:System.Activities.OutArgument%601>, с которым возобновляется <xref:System.Activities.Bookmark>.`Prompt` является <xref:System.Activities.Activity%601>\<string\>, который принимает <xref:System.Activities.InArgument%601>\<string\> с именем `Text` и возвращает пользовательский ответ в `Result`<xref:System.Activities.OutArgument%601>\<string\>.Действие `Prompt` использует действия <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.WriteLine>, поставляемые совместно с платформой .NET Framework, а также содержит пользовательское действие `ReadLine` для получения ввода пользователя.Последним пользовательским действием является действие `Survey`.Это действие <xref:System.Activities.Activity>\<ICollection\<string\>\>.Действие принимает аргумент <xref:System.Activities.InArgument%601>\<IEnumerable\<string\>\>, с именем `Questions` и заполняет выходной аргумент `Result` ответами.Действие `Survey` использует действия <xref:System.Activities.Statements.ForEach>, <xref:System.Activities.Statements.Sequence> и <xref:System.Activities.Statements.AddToCollection%601>, поставляемые совместно с платформой .NET Framework, а также использует действие `Prompt` для задания вопросов из опроса и получения ответов.  
  
#### Настройка, построение и выполнение образца  
  
1.  Откройте образец решения **BasicActivityComposition.sln** в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## См. также