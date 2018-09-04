---
title: Подтверждение
ms.date: 03/30/2017
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
ms.openlocfilehash: caa712aa52da01ce44335a361fd6c9f5215316bf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661000"
---
# <a name="confirmation"></a>Подтверждение
В данном образце показаны четыре общих сценария, связанных с использованием <xref:System.Activities.Statements.CompensableActivity> и подтверждением. Для демонстрации подтверждения в образце запускаются четыре рабочих процесса. Доступны декларативная и императивная версии образца.  
  
## <a name="confirm-a-compensable-activity"></a>Подтверждение действия, подлежащего компенсации  
 Первый рабочий процесс показывает, как подтверждать действие, подлежащее компенсации. Он состоит из двух последовательных экземпляров <xref:System.Activities.Statements.CompensableActivity>. После завершения второго экземпляра <xref:System.Activities.Statements.CompensableActivity> подтверждается первое действие. После успешного завершения рабочего процесса неподтвержденные и некомпенсированные экземпляры <xref:System.Activities.Statements.CompensableActivity> автоматически подтверждаются в порядке по умолчанию. Без подтверждения второй экземпляр <xref:System.Activities.Statements.CompensableActivity> был бы подтвержден первым.  
  
## <a name="explicit-compensation"></a>Явная компенсация  
 Во втором сценарии показано влияние на подтверждение по умолчанию в случае явной компенсации экземпляра <xref:System.Activities.Statements.CompensableActivity>. Рабочий процесс состоит из двух последовательных действий <xref:System.Activities.Statements.CompensableActivity>. После завершения второго действия первое подвергается явной компенсации. В результате, по завершении рабочего процесса подтверждается только второй экземпляр <xref:System.Activities.Statements.CompensableActivity>.  
  
## <a name="controlling-the-order-of-confirmation-for-nested-compensableactivity-activities"></a>Управление порядком подтверждения для вложенных действий CompensableActivity.  
 В третьем сценарии показано, как управлять порядком подтверждения для вложенных действий <xref:System.Activities.Statements.CompensableActivity>CompensableActivity. Корнем рабочего процесса в сценарии является <xref:System.Activities.Statements.CompensableActivity>. Текст корня <xref:System.Activities.Statements.CompensableActivity> представляет собой последовательность из трех <xref:System.Activities.Statements.CompensableActivity>. Обработчик <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> для корня <xref:System.Activities.Statements.CompensableActivity> представляет последовательность, согласно которой подтверждается сначала первый вложенный экземпляр <xref:System.Activities.Statements.CompensableActivity>, а потом второй. По завершении рабочего процесса подтверждается корень <xref:System.Activities.Statements.CompensableActivity>, который затем подтверждает первый, второй и третий вложенные экземпляры <xref:System.Activities.Statements.CompensableActivity> в этом порядке. В результате по умолчанию порядок подтверждения по сути меняется на противоположный. Поскольку третий экземпляр <xref:System.Activities.Statements.CompensableActivity> не подтверждался явно как часть корня <xref:System.Activities.Statements.CompensableActivity> обработчиком <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>, он подтверждается в порядке по умолчанию. Хотя, поскольку это единственный запрос <xref:System.Activities.Statements.CompensableActivity>, оставшийся неподтвержденным, он просто подтверждается.  
  
## <a name="scoping-of-variables"></a>Видимость переменных  
 В четвертом сценарии показано, что время существования переменных, определенные для <xref:System.Activities.Statements.CompensableActivity> или одного из его родительских элементов, остаются в области, даже когда обработчики компенсации <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> или <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> исполняются после завершения действия или рабочего процесса. Рабочий процесс состоит из двух последовательных экземпляров <xref:System.Activities.Statements.CompensableActivity>. В тексте первого переменной `mySum` задается значение, равное 5 + 10 + выведенный результат. В тексте второго <xref:System.Activities.Statements.CompensableActivity> сумме задается значение, равное готовая сумма + 7 + выведенный результат. Для первого экземпляра <xref:System.Activities.Statements.CompensableActivity> задается пользовательский обработчик, который выводит сумму, вычитает из нее 7 и выводит ее заново. Анализ выведенной суммы ясно показывает, что переменная остается в области не только для тел обоих экземпляров <xref:System.Activities.Statements.CompensableActivity>, но и для <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Загрузите решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Запустите приложение ConfirmationSample.exe.  
  
3.  Проверьте следующие выходные данные:  
  
 **Явное подтверждение: начало workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: подтверждение HandlerEnd из workflowCompensableActivity2: подтверждение HandlerExplicit compensation: Start workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: HandlerEnd компенсации из workflowCompensableActivity2: подтверждение HandlerCustom подтверждение обработчика: начало workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd из workflowCompensableActivity1: подтверждение HandlerCompensableActivity2: подтверждение HandlerCompensableActivity3: подтверждение HandlerVariable доступ в обработчике подтверждения: Начало workflowCompensableActivity1: BodyCompensableActivity1: сумма: 15CompensableActivity2: BodyCompensableActivity2: Добавление 7 к sumCompensableActivity2: теперь является сумма: 22End из workflowCompensableActivity2: подтверждение HandlerCompensableActivity1: Подтверждение HandlerCompensableActivity2: сумма: 22CompensableActivity2: после вычитания 12 сумма является теперь: 10Press ввод для выхода.**  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`