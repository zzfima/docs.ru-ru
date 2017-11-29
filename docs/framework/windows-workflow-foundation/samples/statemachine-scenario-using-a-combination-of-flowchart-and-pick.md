---
title: "Сценарий конечного автомата с использованием сочетания действий FlowChart и Pick"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0fb0364310c8780dd41c5369e6b1851dee668d15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a>Сценарий конечного автомата с использованием сочетания действий FlowChart и Pick
Этот образец показывает, как реализовать сценарий простого контрольного таймера с помощью сочетания действий <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Pick>. Для прослушивания событий контрольного таймера используются операции Receive и Send, заданные в действии Pick.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу загрузки, чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В следующей таблице перечислены проекты данного образца.  
  
|Имя проекта|Описание|  
|-|-|  
|StopWatchService|Данный проект реализует конечный автомат для образца контрольного таймера, использующий сочетание действий <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Pick>.<br /><br /> Действие <xref:System.Activities.Statements.Pick> имеет 3 оператора <xref:System.Activities.Statements.PickBranch> в свойстве <xref:System.Activities.Statements.Pick.Branches%2A>, которые прослушивают события `GetStart`, `GetStop` и `GetOff`. В зависимости от входящего события активируются триггеры одной из ветвей, и выполняется соответствующее действие <xref:System.Activities.Statements.PickBranch.Action%2A>. В свойстве <xref:System.Activities.Statements.PickBranch.Action%2A> имеется оператор <xref:System.Activities.Statements.Switch%601>, который определяет допустимость перехода и, если такой переход допустим, свойство `currentState` обновляется до состояния перехода и передается клиенту.<br /><br /> Действие <xref:System.Activities.Statements.FlowDecision>, выполняемое в конце <xref:System.Activities.Statements.Flowchart>, осуществляет расчет свойства `currentState`, чтобы определить, достигло ли оно завершающего состояния. Если переход в завершающее состояние осуществлен, рабочий процесс заканчивается. В противном случае управление передается к началу действия <xref:System.Activities.Statements.Pick>, где рабочий процесс будет ожидать наступления следующих событий контрольного таймера.|  
|StopWatchClient|Представляет собой простое консольное приложение, состоящее из последовательности рабочих процессов, отправляющих различные события контрольного таймера посредством простых сочетаний действий Send и Receive.|  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения StateMachineWithPick.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Запуск StopWatchService.exe из [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] от имени администратора, щелкнув правой кнопкой мыши файл .exe и выбрав **Запуск от имени администратора**.  
  
    1.  Перейдите в папку StateMachineWithPick\CS\StopWatchService\bin\Debug.  
  
    2.  Щелкните правой кнопкой мыши файл StopWatchService.exe и выберите **Запуск от имени администратора**.  
  
4.  Запустите клиентское приложение StopWatchClient из [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  В **обозревателе решений**выберите **StopWatchClient** проект и щелкните правой кнопкой мыши **Назначить запускаемым проектом**.  
  
    2.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
5.  Перейдите обратно в окно консоли приложения StopWatchService.exe, чтобы наблюдать за переходами состояний.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="see-also"></a>См. также
