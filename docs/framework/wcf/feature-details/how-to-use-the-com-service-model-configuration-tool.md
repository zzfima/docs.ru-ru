---
title: Как выполнить Используйте средство настройки модели служб COM +
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: 528e46a47daa6df865308592eb41658369a74b6e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736251"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a>Как выполнить Используйте средство настройки модели служб COM +
Выбрав нужный режим размещения, с помощью программы командной строки настройки модели служб COM+ (ComSvcConfig.exe) сконфигурируйте интерфейсы приложения, предоставляемые как веб-службы.  
  
> [!NOTE]
>  Для выполнения каждой из следующих задач необходимо быть администратором компьютера.  
  
 При использовании ComSvcConfig.exe на компьютере под управлением Windows 7 для настройки веб-службы на использование последней версии модели службы (в настоящее время v4.5) выполните следующие действия.  
  
1.  Настройте раздел реестра `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` значение DWORD 0x00000001  
  
2.  Запустите comsvcconfig.exe  
  
3.  Верните ключу реестра, добавленному на шаге 1, исходное значение или удалите его, если нет.  
  
> [!IMPORTANT]
>  Восстановление значения ключа - важно. Это ключ совместимости. Если не восстановить значение ключа, могут возникнуть проблемы в работе других приложений .NET на данном компьютере.  
  
> [!WARNING]
>  При использовании ComSvcConfig.exe/Install / на компьютере под управлением Windows 8 диалоговое окно отображается уведомление о «приложению на вашем Компьютере требуется следующий компонент Windows: .NET Framework 3.5 (включает .NET 2.0 и .NET 3.0» Если .NET Framework 3.5 не устанавливается. Это диалоговое окно можно пропустить. В качестве альтернативы можно задать ключу реестра OnlyUseLatestCLR значение DWORD 0x00000001  
  
### <a name="to-add-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-com-hosting-mode"></a>Добавление интерфейса в набор интерфейсов, предоставляемых как веб-службы, с помощью режима размещения COM+  
  
-   Выполните программу ComSvcConfig с параметрами `/install` и `/hosting:complus`, как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     Эта команда добавляет интерфейс `IFinances` компонента `ItemOrders.IFinancial` (из приложения COM+ OnlineStore) в набор интерфейсов, предоставляемых как веб-службы. Данная служба использует режим размещения COM+, а потому для нее требуется явное включение приложения.  
  
     Можно использовать подстановочный знак - звездочку (*) для компонента и интерфейса, однако это не рекомендуется, поскольку зачастую желательно предоставлять в качестве веб-службы лишь определенный набор функциональных возможностей. При использовании с более новой версией компонента подстановочный знак может (вопреки замыслу разработчика) предоставить интерфейсы, отсутствовавшие на момент определения синтаксиса конфигурации.  
  
     При использовании параметра /verbose программа отображает предупреждения (помимо ошибок).  
  
     Контракт для предоставленной службы содержит все методы интерфейса `IFinances`.  
  
### <a name="to-add-only-specific-methods-from-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-com-hosting-mode"></a>Добавление только определенных методов интерфейса в набор интерфейсов, предоставляемых как веб-службы, с помощью режима размещения COM+  
  
-   Запустите программу ComSvcConfig с параметрами `/install` и `/hosting:complus`, явно указав имена требуемых методов, как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     Эта команда добавляет только методы `Credit` и `Debit` из интерфейса `IFinances` как операции в контракт предоставляемой службы. Все прочие методы интерфейса не добавляются в контракт и не вызываются клиентами веб-службы.  
  
### <a name="to-add-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-web-hosting-mode"></a>Добавление интерфейса в набор интерфейсов, предоставляемых как веб-службы, с помощью режима размещения на веб-сервере  
  
-   Выполните программу ComSvcConfig с параметрами `/install` и `/hosting:was`, как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     Эта команда добавляет интерфейс `IStockLevels` компонента `ItemInventory.Warehouse` (из приложения COM+ OnlineWarehouse) в набор интерфейсов, предоставляемых как веб-службы. Служба размещается на веб-сервере в виртуальном каталоге OnlineWarehouse службы IIS, а не COM+, а потому приложение включается автоматически по мере необходимости.  
  
     Чтобы воспользоваться конфигурацией с внутрипроцессным размещением на веб-сервере, приложение COM+ необходимо настроить для запуска как библиотечное приложение, а не серверное (с помощью консоли администрирования "Службы компонентов"). Приложения, настроенные как серверные, используют стандартный режим размещения на веб-сервере, что приводит к переходам процесса при обработке каждого запроса.  
  
     Параметр `/mex` добавляет дополнительную конечную точку службы обмена метаданными (MEX), использующую тот же транспорт, что и конечная точка службы приложения, для поддержки клиентов, которым требуется извлечь определение контракта от службы.  
  
### <a name="to-remove-a-web-service-for-a-specified-interface"></a>Удаление веб-службы для указанного интерфейса  
  
-   Выполните программу ComSvcConfig с параметром `/uninstall`, как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     Эта команда удаляет интерфейс `IFinances` компонента `ItemOrders.Financial` (из приложения COM+ OnlineStore).  
  
### <a name="to-list-currently-exposed-interfaces"></a>Вывод списка интерфейсов, предоставляемых в текущий момент  
  
-   Выполните программу ComSvcConfig с параметром `/list`, как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /list  
    ```  
  
     Эта команда выводит список предоставляемых в данный момент интерфейсов, а также соответствующий адрес и сведения о привязке, областью действия которых является локальный компьютер.  
  
### <a name="to-list-specific-currently-exposed-interfaces"></a>Вывод списка определенных интерфейсов, предоставляемых в текущий момент  
  
-   Выполните программу ComSvcConfig с параметром `/list`, как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     Эта команда выводит список предоставляемых в данный момент интерфейсов, размещенных в COM+, а также соответствующий адрес и сведения о привязке для приложения COM+ OnlineStore на локальном компьютере.  
  
### <a name="to-display-help-on-the-options-that-can-be-used-with-the-utility"></a>Вывод справки о параметрах, используемых с программой  
  
-   Запустите программу ComSvcConfig с параметром /? как показано в следующем примере.  
  
    ```  
    ComSvcConfig.exe /?  
    ```  
  
## <a name="see-also"></a>См. также
- [Общие сведения об интеграции с приложениями COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
