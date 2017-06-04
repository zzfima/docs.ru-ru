---
title: "Сохранение приложения рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: abcff14c-f047-4195-ba26-d27f4a82c24e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Сохранение приложения рабочего процесса
Этот образец демонстрирует, как запускать приложение <xref:System.Activities.WorkflowApplication>, выгружать его при переходе в состояние бездействия и снова загружать для продолжения выполнения.  
  
## Подробные сведения об образце  
 <xref:System.Activities.WorkflowApplication> представляет собой узел для одиночного экземпляра рабочего процесса, имеющий простой интерфейс и реализующий несколько наиболее общих вариантов размещения.Одним из таких сценариев является организация продолжительных рабочих процессов с использованием операций сохранения.Управление сохраняемостью в узле осуществляется либо посредством вызова операции сохранения в приложении <xref:System.Activities.WorkflowApplication>, либо посредством обработки события <xref:System.Activities.WorkflowApplication> с указанием того, что именно должно сохранить приложение <xref:System.Activities.WorkflowApplication>.  
  
 Образцом рабочего процесса может служить действие <xref:System.Activities.Statements.WriteLine>, предлагающее пользователю ввести свое имя, действие `ReadLine`, считывающее имя в качестве входного значения через запрос возобновления <xref:System.Activities.Bookmark>, или другое действие <xref:System.Activities.Statements.WriteLine>, отображающее приветствие пользователю.Время ожидания рабочим процессом входных данных — это естественный момент для запуска операций сохранения.Это часто называют точкой <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent>.<xref:System.Activities.WorkflowApplication> вызывает событие <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent> всякий раз, когда программа рабочего процесса может быть сохранена, ожидает возобновления закладки и когда не выполняются никакие другие работы.В данном образце рабочего процесса этот момент наступает сразу после выполнения действия `ReadLine`.  
  
 Для выполнения операций сохранения над <xref:System.Runtime.Persistence.InstanceStore> осуществляется настройка <xref:System.Activities.WorkflowApplication>.В этом образце используется привязка <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.Значение <xref:System.Runtime.Persistence.InstanceStore> необходимо назначить свойству <xref:System.Activities.WorkflowApplication.InstanceStore%2A> до запуска приложения <xref:System.Activities.WorkflowApplication>.  
  
 В этом образце происходит добавление обработчика к событию <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>.Обработчик этого события, возвращая действие <xref:System.Activities.PersistableIdleAction>, указывает, что должно делать приложение <xref:System.Activities.WorkflowApplication>.Если возвращается действие <xref:System.Activities.PersistableIdleAction>, приложение <xref:System.Activities.WorkflowApplication> будет выгружено.  
  
 Данный образец затем принимает входное значение от пользователя и загружает сохраненный рабочий процесс в новое приложение <xref:System.Activities.WorkflowApplication>.Это делается посредством создания нового приложения <xref:System.Activities.WorkflowApplication>, восстановления <xref:System.Runtime.Persistence.InstanceStore>, и сопоставления завершенных и выгруженных событий в экземпляре и затем вызова <xref:System.Activities.WorkflowApplication.Load%2A> с идентификатором экземпляра целевого рабочего процесса.После получения экземпляра закладка активности `ReadLine` возобновляется.Рабочий процесс продолжает выполняться в рамках действия `ReadLine` вплоть до завершения.После завершения и выгрузки рабочего процесса еще один раз \(последний\) вызывается метод <xref:System.Runtime.Persistence.InstanceStore> для удаления рабочего процесса.  
  
#### Использование этого образца  
  
1.  Откройте окно командной строки [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
     Этот образец требует наличия SQL Server Express, устанавливаемого по умолчанию вместе с [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в каталог образцов \(\\WF\\Basic\\Persistence\\InstancePersistence\\CS\) и запустите команду CreateInstanceStore.cmd.  
  
    > [!CAUTION]
    >  Скрипт CreateInstanceStore.cmd создает базу данных в экземпляре SQL Server 2008 Express по умолчанию.Чтобы установить базу данных в другом экземпляре, измените скрипт.  
  
3.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения Persistence.sln и нажмите клавиши CTRL\+SHIFT\+B для построения решения.  
  
    > [!CAUTION]
    >  Если база данных установлена в именованном экземпляре SQL Server, обновите строку соединения в коде перед построением решения.  
  
4.  С правами администратора запустите образец. Для этого перейдите в каталог исполняемых файлов \(\\WF\\Basic\\Persistence\\InstancePersistence\\bin\\Debug\) проекта в[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], щелкните правой кнопкой мыши файл Workflow.exe и выберите команду **Запуск от имени администратора**.  
  
#### Удаление базы данных хранилища экземпляров  
  
1.  Откройте окно командной строки [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Перейдите в каталог образцов и запустите команду RemoveInstanceStore.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Persistence\InstancePersistence`  
  
## См. также  
 [Образцы размещения и сохраняемости AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)