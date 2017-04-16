---
title: "Подтверждение | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Подтверждение
В данном образце показаны четыре общих сценария, связанных с использованием <xref:System.Activities.Statements.CompensableActivity> и подтверждением.Для демонстрации подтверждения в образце запускаются четыре рабочих процесса.Доступны декларативная и императивная версии образца.  
  
## Подтверждение действия, подлежащего компенсации  
 Первый рабочий процесс показывает, как подтверждать действие, подлежащее компенсации. Он состоит из двух последовательных экземпляров <xref:System.Activities.Statements.CompensableActivity>.После завершения второго экземпляра <xref:System.Activities.Statements.CompensableActivity> подтверждается первое действие.После успешного завершения рабочего процесса неподтвержденные и некомпенсированные экземпляры <xref:System.Activities.Statements.CompensableActivity> автоматически подтверждаются в порядке по умолчанию.Без подтверждения второй экземпляр <xref:System.Activities.Statements.CompensableActivity> был бы подтвержден первым.  
  
## Явная компенсация  
 Во втором сценарии показано влияние на подтверждение по умолчанию в случае явной компенсации экземпляра <xref:System.Activities.Statements.CompensableActivity>.Рабочий процесс состоит из двух последовательных действий <xref:System.Activities.Statements.CompensableActivity>. После завершения второго действия первое подвергается явной компенсации.В результате, по завершении рабочего процесса подтверждается только второй экземпляр <xref:System.Activities.Statements.CompensableActivity>.  
  
## Управление порядком подтверждения для вложенных действий CompensableActivity.  
 В третьем сценарии показано, как управлять порядком подтверждения для вложенных действий <xref:System.Activities.Statements.CompensableActivity>CompensableActivity.Корнем рабочего процесса в сценарии является <xref:System.Activities.Statements.CompensableActivity>.Текст корня <xref:System.Activities.Statements.CompensableActivity> представляет собой последовательность из трех <xref:System.Activities.Statements.CompensableActivity>.Обработчик <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> для корня <xref:System.Activities.Statements.CompensableActivity> представляет последовательность, согласно которой подтверждается сначала первый вложенный экземпляр <xref:System.Activities.Statements.CompensableActivity>, а потом второй.По завершении рабочего процесса подтверждается корень <xref:System.Activities.Statements.CompensableActivity>, который затем подтверждает первый, второй и третий вложенные экземпляры <xref:System.Activities.Statements.CompensableActivity> в этом порядке.В результате по умолчанию порядок подтверждения по сути меняется на противоположный.Поскольку третий экземпляр <xref:System.Activities.Statements.CompensableActivity> не подтверждался явно как часть корня <xref:System.Activities.Statements.CompensableActivity> обработчиком <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>, он подтверждается в порядке по умолчанию.Хотя, поскольку это единственный запрос <xref:System.Activities.Statements.CompensableActivity>, оставшийся неподтвержденным, он просто подтверждается.  
  
## Видимость переменных  
 В четвертом сценарии показано, что время существования переменных, определенных для <xref:System.Activities.Statements.CompensableActivity> или одного из его родительских элементов, остается в области при выполнении обработчиков <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> или <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, даже если действие или рабочий процесс уже завершены.Рабочий процесс состоит из двух последовательных экземпляров <xref:System.Activities.Statements.CompensableActivity>.В тексте первого переменной `mySum` задается значение, равное 5 \+ 10 \+ выведенный результат.В тексте второго <xref:System.Activities.Statements.CompensableActivity> сумме задается значение, равное готовая сумма \+ 7 \+ выведенный результат.Для первого экземпляра <xref:System.Activities.Statements.CompensableActivity> задается пользовательский обработчик, который выводит сумму, вычитает из нее 7 и выводит ее заново.Анализ выведенной суммы ясно показывает, что переменная остается в области не только для текстов обоих экземпляров <xref:System.Activities.Statements.CompensableActivity>, но и для <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.  
  
#### Выполнение образца  
  
1.  Загрузите решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Запустите приложение ConfirmationSample.exe.  
  
3.  Проверьте следующие выходные данные:  
  
 **Явное подтверждение: Начало workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Подтверждение HandlerEnd workflowCompensableActivity2: Confirmation HandlerExplicit compensation: Начало workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Подтверждение HandlerEnd workflowCompensableActivity2: Обработчик подтверждения Подтверждение HandlerCustom:Начало workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd workflowCompensableActivity1: Подтверждение HandlerCompensableActivity2: Подтверждение HandlerCompensableActivity3: Подтверждение доступа HandlerVariable в обработчике подтверждения: начало workflowCompensableActivity1: BodyCompensableActivity1: Сумма составляет: 15CompensableActivity2: BodyCompensableActivity2: добавить 7 к sumCompensableActivity2: Теперь сумма составляет: 22End workflowCompensableActivity2: Confirmation HandlerCompensableActivity1: Подтверждение HandlerCompensableActivity2: Сумма составляет: 22CompensableActivity2: После вычитания 12 сумма составляет: 10Press ENTER, чтобы выйти.**  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`  
  
## См. также