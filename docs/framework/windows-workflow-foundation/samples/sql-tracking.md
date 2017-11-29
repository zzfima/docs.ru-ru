---
title: "Отслеживание SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dcffb306c8466e63e0d5888c91d5f6015845d81c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="sql-tracking"></a>Отслеживание SQL
Этот образец показывает, как создать настраиваемый участник отслеживания SQL, который вносит записи отслеживания в базу данных SQL. [!INCLUDE[wf](../../../../includes/wf-md.md)] предоставляет отслеживание рабочего процесса для обеспечения видимости выполнения экземпляра рабочего процесса. Среда выполнения отслеживания выдает записи отслеживания рабочего процесса в ходе его выполнения. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]рабочий процесс отслеживания, в разделе [отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Убедитесь, что на компьютере установлен SQL Server 2008, SQL Server 2008 Express или более новая версия. Скрипты, упакованные в состав образца, предполагают использование экземпляра SQL Express на локальном компьютере пользователя. Если вы работаете с другим экземпляром, до запуска образца следует внести изменения в скрипты, относящиеся к базе данных.  
  
2.  Создание базы данных отслеживания на SQL Server посредством запуска команды Trackingsetup.cmd в каталоге скриптов (\WF\Basic\Tracking\SqlTracking\CS\Scripts). Создает базу данных с именем TrackingSample.  
  
    > [!NOTE]
    >  Этот скрипт создает базу данных на экземпляре SQL Express по умолчанию. Если установку необходимо произвести на другом экземпляре базы данных, внесите изменения в скрипт Trackingsetup.cmd.  
  
3.  Откройте файл решения SqlTrackingSample.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
5.  Нажмите клавишу F5 для запуска приложения.  
  
     Откроется окно браузера со списком каталогов для приложения.  
  
6.  Щелкните файл StockPriceService.xamlx в браузере.  
  
7.  В браузере отображается страница StockPriceService, содержащая адрес WSDL локальной службы. Скопируйте этот адрес.  
  
     Примером адреса WSDL локальной службы является http://localhost:53797/StockPriceService.xamlx?wsdl.  
  
8.  С помощью [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] запустите клиент тестирования WCF (WcfTestClient.exe). Этот файл размещается в каталоге Microsoft Visual Studio 10.0\Common7\IDE.  
  
9. В тестовом клиенте WCF выберите **файл** и выбрать пункт **добавить службу**. Вставьте в текстовое поле адрес локальной службы. Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.  
  
10. В тестовом клиенте WCF дважды щелкните **GetStockPrice**. При этом откроется `GetStockPrice` операцию, которая принимает один параметр типа в значение `Contoso` и нажмите кнопку **Invoke**.  
  
11. Выданные записи отслеживания будут записаны в базу данных SQL. Чтобы просмотреть записи отслеживания, откройте базу данных TrackingSample в среде SQL Management Studio и перейдите в раздел просмотра таблиц. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SQL Server Management Studio, в разделе [Знакомство с SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645). SQL Server 2008 Management Studio Express можно загрузить [здесь](http://go.microsoft.com/fwlink/?LinkId=180520). Применение запроса select для таблиц выводит соответствующие данные записей отслеживания, хранимых в соответствующих таблицах.  
  
#### <a name="to-uninstall-the-sample"></a>Удаление образца  
  
1.  Запустите скрипт Trackingcleanup.cmd, расположенный в каталоге образцов (\WF\Basic\Tracking\SqlTracking).  
  
    > [!NOTE]
    >  Скрипт Trackingcleanup.cmd пытается удалить базу данных, хранящуюся в SQL Express вашего локального компьютера. При использовании другого экземпляра сервера SQL следует внести изменения в скрипт Trackingcleanup.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>См. также  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
