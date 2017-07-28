---
title: "Выражения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Выражения
В этом образце демонстрируется использование в рабочем процессе базовых выражений.Образец содержит рабочий процесс, который рассчитывает статистику по базовой заработной плате для двух служащих вымышленной компании.Два класса — `Employee` и `SalaryStats` — определяются в файлах Employee.cs и SalaryStats.cs.Эти классы используются в рабочем процессе, который показывает, как выполнять простые арифметические и строковые операции над свойствами переменных сложных типов.  
  
 Рабочий процесс вычисления заработной платы определяется и в XAML, и на C\#, чтобы продемонстрировать два стиля разработки.XAML\-версия содержится в файле SalaryCalculation.xaml. Ее можно просмотреть и изменить в конструкторе рабочих процессов.Версия на C\# находится в файле Program.cs.Выражения, используемые в XAML, соответствуют синтаксису Visual Basic и используют для выполнения действия выражений <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> и <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] выражениях Visual Basic см. в разделе [Выражения Visual Basic](http://go.microsoft.com/fwlink/?LinkId=165912).С другой стороны, выражения на C\# записываются в виде лямбда\-выражений и используют действия выражений <xref:System.Activities.Expressions.LambdaValue%601> и <xref:System.Activities.Expressions.LambdaReference%601>.Написание выражений в форме лямбда\-выражений позволяет компилятору C\# выполнять подсветку синтаксиса и статическую проверку.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] лямбда\-выражения в C\# см. в разделе [Руководство по программированию лямбда\-выражений \(C\#\)](http://go.microsoft.com/fwlink/?LinkId=182082).Если рабочий процесс создается в коде на Visual Basic, используются лямбда\-выражения Visual Basic.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] лямбда\-выражения в Visual Basic см. в разделе [Лямбда\-выражения \(Visual Basic\)](http://go.microsoft.com/fwlink/?LinkId=152437).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] разработка рабочих процессов с помощью кода см. в разделе [Разработка рабочих процессов, действий и выражений с помощью императивного кода](../../../../docs/framework/windows-workflow-foundation//authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
#### Запуск образца  
  
1.  Откройте решение Expressions.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите клавиши CTRL\+SHIFT\+B или выберите команду **Построить решение** в меню **Построение**.  
  
    > [!NOTE]
    >  Чтобы открыть файл SalaryCalculation.xaml в конструкторе Visual Studio, необходимо сначала скомпилировать проект, чтобы классы `Employee` и `SalaryStats` были доступны конструктору.  
  
3.  После успешного построения нажмите клавишу F5 или выберите команду **Начать отладку** в меню **Отладка**.Также вы можете нажать клавиши CTRL\+F5 или выбрать команду **Запуск без отладки** в меню **Отладка**, чтобы запустить выполнение без отладки.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Expressions`  
  
## См. также