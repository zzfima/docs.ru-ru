---
title: Наблюдение за сбоями в работе службы
ms.date: 03/30/2017
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
ms.openlocfilehash: 16ed779f77836fb68cf1edf1e01dbb3c0df01d45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="monitoring-service-operation-failures"></a>Наблюдение за сбоями в работе службы
Если для приложения включено аналитическое отслеживание, сбои в работе службы можно легко отслеживать в обозревателе событий.  В этом разделе показано, как определить момент, в который произошел сбой операции службы, и как определить причину сбоя.  
  
### <a name="determining-service-operation-failure-information"></a>Определение сведений о сбое операции службы  
  
1.  Откройте средство просмотра событий, щелкнув **запустить**, **запуска**и введя `eventvwr.exe`.  
  
2.  Если не включено аналитическое отслеживание, разверните **журналы приложений и служб**, **Microsoft**, **Windows**, **сервер приложений-приложения** . Выберите **представление**, **Отобразить аналитический и отладочный журналы**. Щелкните правой кнопкой мыши **аналитический** и выберите **включить журнал**. Оставьте окно просмотра событий открытым, чтобы можно было просмотреть трассировки после сбоя операции службы.  
  
3.  Затем откройте образец, созданные в [учебник по началу работы](../../../../../docs/framework/wcf/getting-started-tutorial.md) в [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Обратите внимание, что необходимо запустить [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] с правами администратора для создания службы. Если у вас есть [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] образцы, устанавливаемые, можно открыть [Приступая к работе](../../../../../docs/framework/wcf/samples/getting-started-sample.md), который содержит завершенный проект, созданный в учебнике.  
  
4.  В файле Program.cs в проекте «Server» добавьте следующую строку кода к началу метода `Divide` класса `CalculatorService`.  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  В файле Program.cs в проекте «Client» измените значение, назначенное value2, на нуль:  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  Выполните серверное приложение без отладки, нажав **Ctrl + F5**.  
  
7.  Откройте командную строку Visual Studio.  С помощью командной строки перейдите в каталог клиента и запустите клиент.  
  
8.  В окне просмотра событий отключите и обновите аналитический журнал и отсортируйте события по идентификаторам событий.  Найдите событие с кодом события [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), которое описывает сбоя службы.  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  При отправке в обозреватель событий события буферизуются, при этом событие сбоя может не отобразиться сразу.
