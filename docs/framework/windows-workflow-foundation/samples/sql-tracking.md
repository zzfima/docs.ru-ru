---
title: "Отслеживание SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Отслеживание SQL
Этот образец показывает, как создать пользовательский участник отслеживания SQL, который вносит записи отслеживания в базу данных SQL.[!INCLUDE[wf](../../../../includes/wf-md.md)] предоставляет отслеживание рабочего процесса для обеспечения видимости выполнения экземпляра рабочего процесса.Среда выполнения отслеживания выдает записи отслеживания рабочего процесса в ходе его выполнения.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] отслеживании рабочих процессов см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  
  
#### Использование этого образца  
  
1.  Убедитесь, что на компьютере установлен SQL Server 2008, SQL Server 2008 Express или более новая версия.Скрипты, входящие в состав образца, предполагают использование экземпляра SQL Express на локальном компьютере пользователя.Если вы работаете с другим экземпляром, до запуска образца следует внести изменения в скрипты, относящиеся к базе данных.  
  
2.  Создание базы данных отслеживания на SQL Server посредством запуска команды Trackingsetup.cmd в каталоге скриптов \(\\WF\\Basic\\Tracking\\SqlTracking\\CS\\Scripts\).Создает базу данных с именем TrackingSample.  
  
    > [!NOTE]
    >  Этот скрипт создает базу данных на экземпляре SQL Express по умолчанию.Если установку необходимо произвести на другом экземпляре базы данных, внесите изменения в скрипт Trackingsetup.cmd.  
  
3.  Откройте файл решения SqlTrackingSample.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Чтобы построить решение, нажмите CTRL\+SHIFT\+B.  
  
5.  Нажмите клавишу F5, чтобы запустить приложение.  
  
     Откроется окно браузера со списком каталогов для приложения.  
  
6.  Щелкните файл StockPriceService.xamlx в браузере.  
  
7.  В браузере отображается страница StockPriceService, содержащая адрес WSDL локальной службы.Скопируйте этот адрес.  
  
     Примером адреса WSDL локальной службы является http:\/\/localhost:53797\/StockPriceService.xamlx?wsdl.  
  
8.  Используя [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], запустите тестовый клиент WCF \(WcfTestClient.exe\).Этот файл размещается в каталоге Microsoft Visual Studio 10.0\\Common7\\IDE.  
  
9. В тестовом клиенте WCF войдите в меню **Файл** и выберите команду **Добавить службу**.Вставьте в текстовое поле адрес локальной службы.Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
10. В тестовом клиенте WCF дважды щелкните метод **GetStockPrice**.Откроется операция `GetStockPrice`, для выполнения которой требуется один параметр, задайте для этого параметра значение `Contoso` и нажмите кнопку **Вызвать**.  
  
11. Выданные записи отслеживания будут записаны в базу данных SQL.Чтобы просмотреть записи отслеживания, откройте базу данных TrackingSample в среде SQL Management Studio и перейдите в раздел просмотра таблиц.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о среде SQL Server Management Studio см. в разделе [Введение в SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).Среду SQL Server 2008 Management Studio Express можно загрузить [здесь](http://go.microsoft.com/fwlink/?LinkId=180520).Применение запроса select для таблиц выводит соответствующие данные записей отслеживания, хранимых в соответствующих таблицах.  
  
#### Удаление образца  
  
1.  Запустите скрипт Trackingcleanup.cmd, расположенный в каталоге образцов \(\\WF\\Basic\\Tracking\\SqlTracking\).  
  
    > [!NOTE]
    >  Скрипт Trackingcleanup.cmd пытается удалить базу данных, хранящуюся в SQL Express на локальном компьютере.При использовании другого экземпляра сервера SQL следует внести изменения в скрипт Trackingcleanup.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## См. также  
 [Образцы наблюдения за AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)