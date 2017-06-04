---
title: "Использование переменных с набором правил из .NET Framework 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Использование переменных с набором правил из .NET Framework 3.5
В этом образце демонстрируется создание рабочего процесса, использующего действие <xref:System.Activities.Statements.Interop> для интеграции настраиваемого действия, записанного в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] с применением политики и правил.Рабочий процесс передает данные для пользовательского действия, привязывая переменные к свойствам зависимостей, предоставляемым настраиваемым действием.  
  
## Пошаговое руководство по образцу  
  
#### Проверка TravelRuleLibrary  
  
1.  Откройте файл решения InteropWith35RuleSet.sln в среде [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  Откройте TravelRuleSet.cs в конструкторе рабочих процессов.  
  
     Последовательное пользовательское действие, содержащее <xref:System.Workflow.Activities.PolicyActivity> отражается на экране.  
  
3.  Дважды щелкните действие политики DiscountPolicy для просмотра правил.  
  
     Появится редактор правил, показывая правила.  
  
4.  Щелкните правой кнопкой мыши `DiscountPolicy` и выберите параметр **Просмотр кода** для просмотра побочного C\# кода для действия.  
  
     Проверьте значения свойства зависимости для `DiscountLevel`.Это эквивалентно аргументам в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].[!INCLUDE[crabout](../../../../includes/crabout-md.md)] аргументах см. в разделе [Переменные и аргументы](../../../../docs/framework/windows-workflow-foundation//variables-and-arguments.md).  
  
## InteropWith35RuleSet  
 Это проект последовательного рабочего процесса, использующий действие <xref:System.Activities.Statements.Interop> для интеграции с пользовательским набором правил, создаваемым в проекте `TravelRuleLibrary`.Переменные создаются при действии верхнего уровня <xref:System.Activities.Statements.Sequence>.Действие <xref:System.Activities.Statements.Interop> используется для интеграции с действием `TravelRuleSet`.Переменные, объявленные в <xref:System.Activities.Statements.Sequence>, используются для привязки к свойствам зависимости.  
  
## Использование этого образца  
  
1.  Откройте файл решения InteropWith35RuleSet.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`  
  
## См. также