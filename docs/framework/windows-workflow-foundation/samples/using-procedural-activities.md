---
title: Использование процедурных действий
ms.date: 03/30/2017
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
ms.openlocfilehash: 787e61a989cb5769461f5155738520dea4609d1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-procedural-activities"></a>Использование процедурных действий
В образце действия <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> и <xref:System.Activities.Statements.WriteLine> используются для реализации игры по угадыванию числа. В игре по угадыванию числа компьютер выбирает случайное число, а игрок должен угадать это число. Если игрок дает неверный ответ, рабочий процесс подсказывает, является ли загаданное число большим или меньшим предложенного. Если игрок угадывает число менее чем за 7 попыток, отображается особое поздравление.  
  
## <a name="custom-activities-in-this-sample"></a>Пользовательские действия в этом образце  
  
### <a name="readline"></a>ReadLine  
 Считывает строку текста из консоли. Это действие является производным от класса <xref:System.Activities.NativeActivity> и создает закладку, которая возобновляется консольным приложением при прочтении строки.  
  
### <a name="promptint"></a>PromptInt  
 Предлагает пользователю ввести число, затем считывает это число из окна консоли. Действие является производным от <xref:System.Activities.Activity%601> и использует действия <xref:System.Activities.Statements.WriteLine> и `ReadLine`.  
  
##### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения GuessingGame.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`