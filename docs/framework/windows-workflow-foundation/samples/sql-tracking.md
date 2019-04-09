---
title: Отслеживание SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 6d3974cbf181734f2a3cab0fbc7d8f32c16699bf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146345"
---
# <a name="sql-tracking"></a>Отслеживание SQL
Этот образец показывает, как создать настраиваемый участник отслеживания SQL, который вносит записи отслеживания в базу данных SQL. Windows Workflow Foundation (WF) предоставляет отслеживание для обеспечения видимости выполнения экземпляра рабочего процесса рабочего процесса. Среда выполнения отслеживания выдает записи отслеживания рабочего процесса в ходе его выполнения. Дополнительные сведения об отслеживании рабочего процесса см. в разделе [отслеживание и трассировка рабочих процессов](../workflow-tracking-and-tracing.md).

#### <a name="to-use-this-sample"></a>Использование этого образца

1.  Убедитесь, что на компьютере установлен SQL Server 2008, SQL Server 2008 Express или более новая версия. Скрипты, упакованные в состав образца, предполагают использование экземпляра SQL Express на локальном компьютере пользователя. Если вы работаете с другим экземпляром, до запуска образца следует внести изменения в скрипты, относящиеся к базе данных.

2.  Создание базы данных отслеживания на SQL Server посредством запуска команды Trackingsetup.cmd в каталоге скриптов (\WF\Basic\Tracking\SqlTracking\CS\Scripts). Создает базу данных с именем TrackingSample.

    > [!NOTE]
    >  Этот скрипт создает базу данных на экземпляре SQL Express по умолчанию. Если установку необходимо произвести на другом экземпляре базы данных, внесите изменения в скрипт Trackingsetup.cmd.  
  
3.  Откройте SqlTrackingSample.sln в Visual Studio 2010.  
  
4.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
5.  Нажмите клавишу F5 для запуска приложения.  
  
     Откроется окно браузера со списком каталогов для приложения.  
  
6.  Щелкните файл StockPriceService.xamlx в браузере.  
  
7.  В браузере отображается страница StockPriceService, содержащая адрес WSDL локальной службы. Скопируйте этот адрес.  
  
     Примером адреса WSDL локальной службы является `http://localhost:65193/StockPriceService.xamlx?wsdl`.  
  
8.  С помощью [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] запустите клиент тестирования WCF (WcfTestClient.exe). Этот файл размещается в каталоге Microsoft Visual Studio 10.0\Common7\IDE.  
  
9. В тестовом клиенте WCF выберите **файл** меню и выберите **добавить службу**. Вставьте в текстовое поле адрес локальной службы. Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.  
  
10. В тестовом клиенте WCF дважды щелкните **GetStockPrice**. Откроется `GetStockPrice` операцию, которая принимает один параметр типа в значение `Contoso` и нажмите кнопку **Invoke**.  
  
11. Выданные записи отслеживания будут записаны в базу данных SQL. Чтобы просмотреть записи отслеживания, откройте базу данных TrackingSample в среде SQL Management Studio и перейдите в раздел просмотра таблиц. Дополнительные сведения о SQL Server Management Studio, см. в разделе [Знакомство с SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645). SQL Server 2008 Management Studio Express можно загрузить [здесь](https://go.microsoft.com/fwlink/?LinkId=180520). Применение запроса select для таблиц выводит соответствующие данные записей отслеживания, хранимых в соответствующих таблицах.  
  
#### <a name="to-uninstall-the-sample"></a>Удаление образца  
  
1.  Запустите скрипт Trackingcleanup.cmd, расположенный в каталоге образцов (\WF\Basic\Tracking\SqlTracking).  
  
    > [!NOTE]
    >  Скрипт Trackingcleanup.cmd пытается удалить базу данных, хранящуюся в SQL Express вашего локального компьютера. При использовании другого экземпляра сервера SQL следует внести изменения в скрипт Trackingcleanup.cmd.

> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>См. также

- [Образцы наблюдения за AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
