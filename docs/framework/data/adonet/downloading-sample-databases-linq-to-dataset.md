---
title: Загрузка примеров баз данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: f2488b0e1bfc578679a2a2802c332439f374a341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763057"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Загрузка примеров баз данных (LINQ to DataSet)
Примеры и пошаговые руководства в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] документации используется образец базы данных AdventureWorks. Этот продукт можно бесплатно загрузить с веб-сайта загрузки Майкрософт. Образцы и пошаговые руководства в документации по [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] используют в качестве хранилища данных SQL Server. Вместо SQL Server можно использовать SQL Server Express Edition, который доступен для бесплатной загрузки.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Загрузка и установка базы данных AdventureWorks  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>Загрузка и установка образца базы данных AdventureWorks для SQL Server  
  
1.  Откройте Internet Explorer.  
  
2.  Последовательно выберите пункты [образцы SQL Server 2005 и образцов баз данных](http://go.microsoft.com/fwlink/?linkid=31046) веб-сайта.  
  
3.  Следуйте инструкциям на веб-узле по загрузке образца базы данных AdventureWorks для соответствующего процессора (например, AdventureWorksDB.msi) и сохраните файл с расширением MSI на компьютер.  
  
4.  Если установлена предыдущая версия AdventureWorks, ее необходимо удалить перед запуском AdventureWorks.msi.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>Удаление предыдущей версии образца базы данных AdventureWorks   
  
1.  Удалите базу данных AdventureWorks или AdventureWorksDW.  
  
2.  Из **Установка и удаление программ**выберите **AdventureWorksDB** или **AdventureWorksBI** и нажмите кнопку **удалить**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>Удаление предыдущей версии образца базы данных AdventureWorks, установленной с помощью программы установки  
  
1.  Удалите базу данных AdventureWorks или AdventureWorksDW.  
  
2.  Из **Установка и удаление программ**выберите **Microsoft SQL Server 2005** и нажмите кнопку **изменений**.  
  
3.  Из **Выбор компонентов**выберите **компоненты рабочей станции** и нажмите кнопку **Далее**.  
  
4.  Из **вас приветствует мастер установки SQL Server**, нажмите кнопку **Далее**.  
  
5.  Из **Проверка конфигурации системы**, нажмите кнопку **Далее**.  
  
6.  Из **изменить или удалить экземпляр**, нажмите кнопку **изменить установленные компоненты**.  
  
7.  Из **Выбор компонентов**, разверните **документация, примеры и образцы баз данных** узла.  
  
8.  Выберите **образцы кода и приложений**. Разверните **образцы баз данных**, выберите образец базы данных, который необходимо удалить и выберите **компонент станет недоступным**. Нажмите кнопку **Далее**.  
  
9. Нажмите кнопку **установить** и завершите работу мастера установки.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>Присоединение файлов образца базы данных AdventureWorks к SQL Server  
  
1.  После загрузки файла установщика образца базы данных, дважды щелкните **AdventureWorksDB.msi** файла (или загруженный файл) для установки базы данных. По умолчанию база данных устанавливается в папку c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.  
  
2.  Подключите файлы базы данных AdventureWorks к экземпляру SQL Server, выполнив следующий скрипт в командной строке SQLCMD или в среде SQL Server Management Studio:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Если файлы были установлены на другой диск или в другой каталог, нужно исправить соответствующие пути перед выполнением хранимой процедуры `sp_attach_db`.  
  
## <a name="downloading-sql-server-express-edition"></a>Загрузка SQL Server Express Edition  
 Примеры и пошаговые руководства в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] раздела, используемая в качестве хранилища данных SQL Server 2005, но можно изменить, чтобы вместо этого используйте SQL Server Express Edition,. SQL Server Express Edition доступен бесплатно и его можно распространять вместе с приложениями. При использовании Visual Studio, SQL Server Express Edition включается в выпусках Pro и более поздних версий.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>Загрузка и установка выпуска SQL Server Express  
  
1.  Запустите Internet Explorer.  
  
2.  Последовательно выберите пункты [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) странице загрузки.  
  
3.  Следуйте указаниям по установке, содержащимся на веб-узле.  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
