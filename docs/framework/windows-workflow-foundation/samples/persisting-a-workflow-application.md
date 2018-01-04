---
title: "Сохранение приложения рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abcff14c-f047-4195-ba26-d27f4a82c24e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf23b8e33766ea7a15135418142082a0e7b715ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="persisting-a-workflow-application"></a>Сохранение приложения рабочего процесса
Этот образец демонстрирует, как запускать приложение <xref:System.Activities.WorkflowApplication>, выгружать его при переходе в состояние бездействия и снова загружать для продолжения выполнения.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 <xref:System.Activities.WorkflowApplication> представляет собой узел для одиночного экземпляра рабочего процесса, имеющий простой интерфейс и реализующий несколько наиболее общих вариантов размещения. Одним из таких сценариев является организация продолжительных рабочих процессов с использованием операций сохранения. Управление сохраняемостью в узле осуществляется либо посредством вызова операции сохранения в приложении <xref:System.Activities.WorkflowApplication>, либо посредством обработки события <xref:System.Activities.WorkflowApplication> с указанием того, что именно должно сохранить приложение <xref:System.Activities.WorkflowApplication>.  
  
 Образцом рабочего процесса может служить действие <xref:System.Activities.Statements.WriteLine>, предлагающее пользователю ввести свое имя, действие `ReadLine`, считывающее имя в качестве входного значения через запрос возобновления <xref:System.Activities.Bookmark>, или другое действие <xref:System.Activities.Statements.WriteLine>, отображающее приветствие пользователю. Время ожидания рабочим процессом входных данных - это естественный момент для запуска операций сохранения. Его часто называют точкой <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle>. <xref:System.Activities.WorkflowApplication> вызывает событие <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle> всякий раз, когда программа рабочего процесса может быть сохранена, ожидает возобновления закладки, и не выполняются никакие другие работы. В данном образце рабочего процесса этот момент наступает сразу после выполнения действия `ReadLine`.  
  
 Объект <xref:System.Activities.WorkflowApplication> настроен для выполнения операций сохранения <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`. В этом образце используется привязка <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>. <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` Должны быть назначены <xref:System.Activities.WorkflowApplication.InstanceStore%2A> свойства перед <xref:System.Activities.WorkflowApplication> выполняется.  
  
 В этом образце происходит добавление обработчика к событию <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>. Обработчик этого события, возвращая действие <xref:System.Activities.WorkflowApplication>, указывает, что должно делать приложение <xref:System.Activities.PersistableIdleAction>. Если возвращается действие <xref:System.Activities.PersistableIdleAction.Unload>, приложение <xref:System.Activities.WorkflowApplication> будет выгружено.  
  
 Данный образец затем принимает входное значение от пользователя и загружает сохраненный рабочий процесс в новое приложение <xref:System.Activities.WorkflowApplication>. Это достигается путем создания нового <xref:System.Activities.WorkflowApplication>, восстановления <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`и сопоставления завершенных и выгруженных событий в экземпляре и последующего вызова <xref:System.Activities.WorkflowApplication.Load%2A> с идентификатор целевого экземпляра рабочего процесса. После получения экземпляра закладка активности `ReadLine` возобновляется. Рабочий процесс продолжает выполняться в рамках действия `ReadLine` вплоть до завершения. Если рабочий процесс завершения и выгрузки <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` вызывается последний раз, чтобы удалить рабочий процесс.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
     Этот образец требует наличия SQL Server Express, устанавливаемого по умолчанию вместе с [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в каталог образцов (\WF\Basic\Persistence\InstancePersistence\CS) и запустите команду CreateInstanceStore.cmd.  
  
    > [!CAUTION]
    >  Скрипт CreateInstanceStore.cmd создает базу данных в экземпляре SQL Server 2008 Express по умолчанию. Чтобы установить базу данных в другом экземпляре, измените скрипт.  
  
3.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения Persistence.sln и нажмите клавиши CTRL+SHIFT+B для сборки решения.  
  
    > [!CAUTION]
    >  Если база данных установлена в именованном экземпляре SQL Server, обновите строку соединения в коде перед построением решения.  
  
4.  Запуск образца с правами администратора, перейдите в каталог проекта (\WF\Basic\Persistence\InstancePersistence\bin\Debug) в [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], щелкнув правой кнопкой мыши Workflow.exe и выберите команду **Запуск от имени администратора**.  
  
#### <a name="to-remove-the-instance-store-database"></a>Удаление базы данных хранилища экземпляров  
  
1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в каталог образцов и запустите команду RemoveInstanceStore.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\InstancePersistence`  
  
## <a name="see-also"></a>См. также  
 [Образцы размещения и сохраняемости образцы](http://go.microsoft.com/fwlink/?LinkId=193961)
