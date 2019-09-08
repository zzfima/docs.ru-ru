---
title: Загрузка примеров баз данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: c67ee699cf594f476a728c7345b47b0c32dea7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795177"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Загрузка примеров баз данных (LINQ to DataSet)
Примеры и пошаговые руководства в документации по LINQ to DataSet используют образец базы данных AdventureWorks. Этот продукт можно бесплатно загрузить с веб-узла корпорации Майкрософт. Примеры и пошаговые руководства в документации по LINQ to DataSet используют SQL Server в качестве хранилища данных. Вместо SQL Server можно использовать SQL Server Express Edition, который доступен для бесплатной загрузки.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Загрузка и установка базы данных AdventureWorks  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>Загрузка и установка образца базы данных AdventureWorks для SQL Server  
  
1. Откройте Internet Explorer.  
  
2. Перейдите на веб-сайт [примеров SQL Server 2005 и образцов баз данных](https://go.microsoft.com/fwlink/?linkid=31046) .  
  
3. Следуйте инструкциям на веб-узле по загрузке образца базы данных AdventureWorks для соответствующего процессора (например, AdventureWorksDB.msi) и сохраните файл с расширением MSI на компьютер.  
  
4. Если установлена предыдущая версия AdventureWorks, ее необходимо удалить перед запуском AdventureWorks.msi.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>Удаление предыдущей версии образца базы данных AdventureWorks  
  
1. Удалите базу данных AdventureWorks или AdventureWorksDW.  
  
2. В меню **Установка и удаление программ**выберите **AdventureWorksDB** или **адвентуреворксби** и нажмите кнопку **Удалить**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>Удаление предыдущей версии образца базы данных AdventureWorks, установленной с помощью программы установки  
  
1. Удалите базу данных AdventureWorks или AdventureWorksDW.  
  
2. В меню **Установка и удаление программ**выберите **Microsoft SQL Server 2005** и нажмите кнопку **изменить**.  
  
3. В списке **компонент**выберите **компоненты рабочей станции** и нажмите кнопку **Далее**.  
  
4. В **мастере установки SQL Server**нажмите кнопку **Далее**.  
  
5. На основе **проверки конфигурации системы**нажмите кнопку **Далее**.  
  
6. В меню **изменить или удалить экземпляр**щелкните **изменить установленные компоненты**.  
  
7. В **области Выбор компонентов**разверните узел **Документация, примеры и примеры баз данных** .  
  
8. Выберите **пример кода и приложений**. Разверните **образец базы данных**, выберите удаляемый образец базы данных и выберите **весь компонент будет недоступен**. Нажмите кнопку **Далее**.  
  
9. Нажмите кнопку **установить** и завершите работу мастера установки.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>Присоединение файлов образца базы данных AdventureWorks к SQL Server  
  
1. После скачивания файла образца базы данных программы установки дважды щелкните файл **AdventureWorksDB. msi** (или скачанный файл), чтобы установить базу данных. По умолчанию база данных устанавливается в папку c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.  
  
2. Подключите файлы базы данных AdventureWorks к экземпляру SQL Server, выполнив следующий скрипт в командной строке SQLCMD или в среде SQL Server Management Studio:  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Если файлы были установлены на другой диск или в другой каталог, нужно исправить соответствующие пути перед выполнением хранимой процедуры `sp_attach_db`.  
  
## <a name="downloading-sql-server-express-edition"></a>Загрузка SQL Server Express Edition  
 Примеры и пошаговые руководства в разделе LINQ to DataSet используют SQL Server 2005 в качестве хранилища данных, но могут быть изменены для использования SQL Server Express Edition. SQL Server Express Edition доступен бесплатно и его можно распространять вместе с приложениями. Если вы используете Visual Studio, SQL Server Express Edition входит в выпуски Pro и выше.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>Загрузка и установка выпуска SQL Server Express  
  
1. Запустите Internet Explorer.  
  
2. Перейдите на страницу загрузки [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) .  
  
3. Следуйте указаниям по установке, содержащимся на веб-узле.  
  
## <a name="see-also"></a>См. также

- [Начало работы](getting-started-linq-to-dataset.md)
