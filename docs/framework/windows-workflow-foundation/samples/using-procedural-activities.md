---
title: "Использование процедурных действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Использование процедурных действий
В образце действия <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> и <xref:System.Activities.Statements.WriteLine> используются для реализации игры по угадыванию числа.В игре по угадыванию числа компьютер выбирает случайное число, а игрок должен угадать это число.Если игрок дает неверный ответ, рабочий процесс подсказывает, является ли загаданное число большим или меньшим предложенного.Если игрок угадывает число менее чем за 7 попыток, отображается особое поздравление.  
  
## Пользовательские действия в этом образце  
  
### ReadLine  
 Считывает строку текста из консоли.Это действие является производным от класса <xref:System.Activities.NativeActivity> и создает закладку, которая возобновляется консольным приложением при прочтении строки.  
  
### PromptInt  
 Предлагает пользователю ввести число, затем считывает это число из окна консоли.Действие является производным от <xref:System.Activities.Activity%601> и использует действия <xref:System.Activities.Statements.WriteLine> и `ReadLine`.  
  
##### Использование этого образца  
  
1.  С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения GuessingGame.sln.  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## См. также