---
title: "Действие IfElse с правилами | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Действие IfElse с правилами
В данном образце демонстрируется использование условий правила для действия класса <xref:System.Workflow.Activities.IfElseActivity>.  
  
 В данном образце из узла передается параметр `OrderValue`.Значение параметра используется в условии правила для первого ответвления действия класса <xref:System.Workflow.Activities.IfElseActivity>.Если значение меньше 10 000, выполняется первое разветвление, а действие <xref:System.Workflow.Activities.CodeActivity> в первом ответвлении выводит в консоль **Get Manager Approval**.Если значение больше 10 000, выполняется действие <xref:System.Workflow.Activities.CodeActivity> во втором разветвлении и выводится **Get VP Approval**.  
  
### Построение образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте решение, нажав клавиши CTRL\+SHIFT\+B.  
  
3.  Запустите решение без отладки, нажав сочетание клавиш CTRL\+F5.  
  
### Запуск образца  
  
-   В окне командной строки пакета SDK запустите файл с расширением EXE в папке «IfElseWithRules\\bin\\debug» \(или в папке «IfElseWithRules\\bin» для образца в Visual Basic\), вложенной в главную папку образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец находится в следующем каталоге:  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## См. также  
 <xref:System.Workflow.Activities.Rules>   
 <xref:System.Workflow.Activities.IfElseActivity>   
 <xref:System.Workflow.Activities.CodeActivity>   
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>