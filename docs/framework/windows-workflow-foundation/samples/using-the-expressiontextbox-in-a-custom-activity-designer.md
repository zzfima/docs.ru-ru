---
title: "Использование ExpressionTextBox в пользовательском конструкторе действия | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Использование ExpressionTextBox в пользовательском конструкторе действия
В этом образце показано, как использовать <xref:System.Activities.Presentation.View.ExpressionTextBox> в настраиваемом конструкторе действий.Пользовательское действие `MultiAssign` присваивает два строковых значения двум строковым переменным.Некоторые элементы управления <xref:System.Activities.Presentation.View.ExpressionTextBox> привязываются к аргументу <xref:System.Activities.InArgument>, а некоторые — к аргументу <xref:System.Activities.OutArgument>.  
  
## Подробные сведения об образце  
 `ArgumentToExpressionConverter` — это преобразователь типов, используемый для привязки выражений к аргументам.Параметр `ConverterParameter` необходимо установить в соответствующее значение `In` или `Out`.`InOut` не поддерживается.  
  
 Атрибут `UseLocationExpression` используется в `OutArgument`, чтобы указать, что выражение должно быть левосторонним.В большинстве случаев левостороннее выражение является допустимым идентификатором Visual Basic, используемым для указания того, что возвращаемый аргумент `OutArgument` является переменной или именем аргумента.  
  
 В этом примере для атрибута `MaxLines` установлено значение 1, а значение атрибута `MinLines` не задано.Это указывает, что текстовое поле <xref:System.Activities.Presentation.View.ExpressionTextBox> имеет фиксированный размер в одну строку независимо от объема текста, введенного пользователем.Чтобы разрешить изменение размера текстового поля <xref:System.Activities.Presentation.View.ExpressionTextBox> в соответствии с объемом вводимых пользователем данных, задайте значение `MaxLines`, которое больше значения `MinLines`.  
  
 Текстовое поле ExpressionTextBox может быть привязано только к аргументам и не может быть привязано к свойствам CLR.  
  
#### Использование этого образца  
  
1.  Откройте файл ExpressionTextBoxSample.sln с помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
#### Запуск этого образца  
  
1.  Добавьте в решение новое консольное приложение рабочего процесса.  
  
2.  Добавьте ссылку на проект **ExpressionTextBoxSample** из нового проекта консольного приложения рабочего процесса.  
  
3.  Постройте решение.  
  
4.  Перетащите действие **MultiAssign** с панели инструментов в рабочий процесс.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## См. также  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>   
 [Разработка приложений с помощью конструктора рабочего процесса](../Topic/Developing%20Applications%20with%20the%20Workflow%20Designer.md)