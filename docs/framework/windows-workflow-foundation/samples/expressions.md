---
title: Expressions2
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c8470a3bb93385724f50e18d25c148ee609c3a77
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="expressions"></a>Выражения
В этом образце демонстрируется использование в рабочем процессе базовых выражений. Образец содержит рабочий процесс, который рассчитывает статистику по базовой заработной плате для двух служащих вымышленной компании. Два класса - `Employee` и `SalaryStats` - определяются в файлах Employee.cs и SalaryStats.cs. Эти классы используются в рабочем процессе, который показывает, как выполнять простые арифметические и строковые операции над свойствами переменных сложных типов.  
  
 Рабочий процесс вычисления заработной платы определяется и в XAML, и на C#, чтобы продемонстрировать два стиля разработки. XAML-версия содержится в файле SalaryCalculation.xaml. Ее можно просмотреть и изменить в конструкторе рабочих процессов. Версия на C# находится в файле Program.cs. Выражения, используемые в XAML, соответствуют синтаксису Visual Basic и используют для выполнения действия выражений <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> и <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601>. Дополнительные сведения о выражениях см. Visual Basic [выражения Visual Basic](http://go.microsoft.com/fwlink/?LinkId=165912). С другой стороны, выражения на C# записываются в виде лямбда-выражений и используют действия выражений <xref:System.Activities.Expressions.LambdaValue%601> и <xref:System.Activities.Expressions.LambdaReference%601>. Написание выражений в форме лямбда-выражений позволяет компилятору C# выполнять подсветку синтаксиса и статическую проверку. Дополнительные сведения о лямбда-выражениях в C# см. в разделе [лямбда-выражения (руководство по программированию на C#)](http://go.microsoft.com/fwlink/?LinkId=182082). Если рабочий процесс создается в коде на Visual Basic, используются лямбда-выражения Visual Basic. Дополнительные сведения о лямбда-выражениях в Visual Basic см. в разделе [лямбда-выражения (Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=152437). Дополнительные сведения о создании рабочих процессов с помощью кода см. в разделе [разработки рабочих процессов, действий и выражений с помощью императивного кода](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение Expressions.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Нажмите клавиши CTRL + SHIFT + B для построения решения или выберите **построить решение** из **построения** меню.  
  
    > [!NOTE]
    >  Чтобы открыть файл SalaryCalculation.xaml в конструкторе Visual Studio, необходимо сначала скомпилировать проект, чтобы классы `Employee` и `SalaryStats` были доступны конструктору.  
  
3.  После успешного построения нажмите клавишу F5 или выберите **начать отладку** из **отладки** меню. Также нажмите клавиши Ctrl + F5 или выбрать команду **Запуск без отладки** из **отладки** меню для запуска без отладки.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`