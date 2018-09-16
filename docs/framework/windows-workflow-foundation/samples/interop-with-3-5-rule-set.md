---
title: Взаимодействие с набором правил 3.5
ms.date: 03/30/2017
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
ms.openlocfilehash: 5ea5454ef80bfd83611ed20392782d99cd8c0c25
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677283"
---
# <a name="interop-with-35-rule-set"></a>Взаимодействие с набором правил 3.5
В этом примере демонстрируется использование <xref:System.Activities.Statements.Interop> для интеграции с пользовательским действием в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] с помощью <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` и правил. Оно передает данные для пользовательского действия, привязывая переменные [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] к свойствам зависимостей, предоставляемым пользовательским действием.  
  
## <a name="requirements"></a>Требования  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a>Демонстрации  
 <xref:System.Activities.Statements.Interop> действие, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` действия в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] со свойствами зависимости  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце демонстрируется один из сценариев интеграции для интеграции с действием [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]. Этот пример включает [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] пользовательское действие, которое вызывает <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` действия.  
  
## <a name="travelrulelibrary"></a>TravelRuleLibrary  
 При открытии TravelRuleSet.cs в конструкторе следующим образом показывается последовательное пользовательское действие, содержащее действие PolicyActivity:  
  
 ![Действие Interop](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")  
  
 Дважды щелкните **DiscountPolicy** действие политики для просмотра правил. Появляется редактор правил, показывающий правила.  
  
 ![Редактор набора правил](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")  
  
 Щелкните правой кнопкой мыши **DiscountPolicy** действие и выберите **Просмотр кода** возможность рассмотреть с кодом C# код, данного действия. Проверьте значения свойства зависимости для `DiscountLevel`. Это эквивалентно <xref:System.Activities.Argument> в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].  
  
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
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 Это проект последовательного рабочего процесса [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], использующий действие <xref:System.Activities.Statements.Interop> для интеграции с пользовательским набором правил, создаваемым в проекте TravelRuleLibrary. Переменные создаются при действии верхнего уровня <xref:System.Activities.Statements.Sequence> следующим образом.  
  
 ![Переменные](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")  
  
 ![Обозреватель решений](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")  
  
 Наконец, действие <xref:System.Activities.Statements.Interop> используется для интеграции с TravelRuleSet. Переменные, объявленные ранее в <xref:System.Activities.Statements.Sequence>, используются для привязки к свойствам зависимости.  
  
 ![Тип действия](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")  
  
 ![Стрелка](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")  
  
 ![Свойства](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`
