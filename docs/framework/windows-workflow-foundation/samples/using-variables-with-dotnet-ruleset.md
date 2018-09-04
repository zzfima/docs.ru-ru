---
title: Использование переменных с набором правил из .NET Framework 3.5
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 64d47564076e19e152e30b6ab0cb3900ce53cfa1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512858"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a>Использование переменных с набором правил из .NET Framework 3.5
В этом образце демонстрируется создание рабочего процесса, использующего действие <xref:System.Activities.Statements.Interop> для интеграции настраиваемого действия, записанного в [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] с применением политики и правил. Рабочий процесс передает данные для пользовательского действия, привязывая переменные к свойствам зависимостей, предоставляемым настраиваемым действием.  
  
## <a name="sample-walkthrough"></a>Пошаговое руководство по образцу  
  
#### <a name="to-examine-travelrulelibrary"></a>Проверка TravelRuleLibrary  
  
1.  Откройте файл решения InteropWith35RuleSet.sln в Visual Studio.  
  
2.  Откройте TravelRuleSet.cs в конструкторе рабочих процессов.  
  
     Последовательное пользовательское действие, содержащее <xref:System.Workflow.Activities.PolicyActivity> отражается на экране.  
  
3.  Дважды щелкните действие политики DiscountPolicy для просмотра правил.  
  
     Появится редактор правил, показывая правила.  
  
4.  Щелкните правой кнопкой мыши `DiscountPolicy` и выберите **Просмотр кода** возможность просмотра побочного C# кода для действия.  
  
     Проверьте значения свойства зависимости для `DiscountLevel`. Это эквивалентно аргументам в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]. Дополнительные сведения об аргументах см. в разделе [переменных и аргументов](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 Это проект последовательного рабочего процесса, использующий действие <xref:System.Activities.Statements.Interop> для интеграции с пользовательским набором правил, создаваемым в проекте `TravelRuleLibrary`. Переменные создаются при действии верхнего уровня <xref:System.Activities.Statements.Sequence>. Действие <xref:System.Activities.Statements.Interop> используется для интеграции с действием `TravelRuleSet`. Переменные, объявленные в <xref:System.Activities.Statements.Sequence>, используются для привязки к свойствам зависимости.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения InteropWith35RuleSet.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`