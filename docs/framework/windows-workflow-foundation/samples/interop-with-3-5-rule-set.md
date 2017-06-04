---
title: "Взаимодействие с набором правил 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Взаимодействие с набором правил 3.5
В этом образце демонстрируется использование действия <xref:System.Activities.Statements.Interop> для интеграции с пользовательским действием в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] с применением <xref:System.Workflow.Activities.Policy> и правил.  Оно передает данные для пользовательского действия, привязывая переменные [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] к свойствам зависимостей, предоставляемым пользовательским действием.  
  
## Требования  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## Демонстрации  
 <xref:System.Activities.Statements.Interop> действие, <xref:System.Workflow.Activities.Policy> действие в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] со свойствами зависимости.  
  
## Обсуждение  
 В этом образце демонстрируется один из сценариев интеграции для интеграции с действием [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)].  Образец включает пользовательское действие [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], вызывающее действие <xref:System.Workflow.Activities.Policy>.  
  
## TravelRuleLibrary  
 При открытии TravelRuleSet.cs в конструкторе следующим образом показывается последовательное пользовательское действие, содержащее действие PolicyActivity:  
  
 ![Действие Interop](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")  
  
 Дважды щелкните действие политики **DiscountPolicy** для просмотра правил.  Появляется редактор правил, показывающий правила.  
  
 ![Редактор наборов правил](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")  
  
 Щелкните правой кнопкой мыши действие **DiscountPolicy** и выберите параметр **Просмотр кода** для просмотра побочного C\# кода для данного действия.  Проверьте значения свойства зависимости для `DiscountLevel`.  Это эквивалентно <xref:System.Activities.Argument> в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].  
  
```  
public static DependencyProperty DiscountLevelProperty = DependencyProperty.Register("DiscountLevel", typeof(int), typeof(TravelRuleSet));  
  
[DescriptionAttribute("DiscountLevel")]  
[CategoryAttribute("DiscountLevel Category")]  
[BrowsableAttribute(true)]  
[DesignerSerializationVisibilityAttribute(DesignerSerializationVisibility.Visible)]  
public int DiscountLevel  
{  
   get  
   {  
return ((int)base.GetValue(TravelRuleSet.DiscountLevelProperty)));  
   }  
   set  
   {  
base.SetValue(TravelRuleSet.DiscountLevelProperty, value);  
   }  
}  
```  
  
## InteropWith35RuleSet  
 Это проект последовательного рабочего процесса [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], использующий действие <xref:System.Activities.Statements.Interop> для интеграции с пользовательским набором правил, создаваемым в проекте TravelRuleLibrary.  Переменные создаются при действии верхнего уровня <xref:System.Activities.Statements.Sequence> следующим образом.  
  
 ![Переменные](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")  
  
 ![Обозреватель решений](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")  
  
 Наконец, действие <xref:System.Activities.Statements.Interop> используется для интеграции с TravelRuleSet.  Переменные, объявленные ранее в <xref:System.Activities.Statements.Sequence>, используются для привязки к свойствам зависимости.  
  
 ![Тип действия](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")  
  
 ![Стрелка](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")  
  
 ![Свойства](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<ДискУстановки>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`