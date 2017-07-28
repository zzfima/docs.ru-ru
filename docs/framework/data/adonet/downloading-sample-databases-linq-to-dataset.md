---
title: "Загрузка образцов баз данных (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Загрузка образцов баз данных (LINQ to DataSet)
В образцах и пошаговых руководствах документации по [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] используется образец базы данных AdventureWorks.  Этот продукт можно бесплатно загрузить с веб\-сайта корпорации Майкрософт. В образцах и пошаговых руководствах документации по [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] в качестве хранилища данных используется SQL Server.  Вместо SQL Server можно использовать SQL Server Express Edition, который доступен для бесплатной загрузки.  
  
## Загрузка и установка базы данных AdventureWorks  
  
#### Загрузка и установка образца базы данных AdventureWorks для SQL Server  
  
1.  Откройте Internet Explorer.  
  
2.  Перейдите на веб\-сайт [Образцы кода и баз данных для SQL Server 2005](http://go.microsoft.com/fwlink/?linkid=31046).  
  
3.  Следуйте инструкциям на веб\-узле по загрузке образца базы данных AdventureWorks для соответствующего процессора \(например, AdventureWorksDB.msi\) и сохраните файл с расширением MSI на компьютер.  
  
4.  Если установлена предыдущая версия AdventureWorks, ее необходимо удалить перед запуском AdventureWorks.msi.  
  
#### Удаление предыдущей версии образца базы данных AdventureWorks  
  
1.  Удалите базу данных AdventureWorks или AdventureWorksDW.  
  
2.  В оснастке **Установка и удаление программ** выберите **AdventureWorksDB** или **AdventureWorksBI** и нажмите кнопку **Удалить**.  
  
#### Удаление предыдущей версии образца базы данных AdventureWorks, установленной с помощью программы установки  
  
1.  Удалите базу данных AdventureWorks или AdventureWorksDW.  
  
2.  В оснастке **Установка и удаление программ** выберите **Microsoft SQL Server 2005** и нажмите кнопку **Изменить**.  
  
3.  В окне **Выбор компонентов** выберите **Компоненты рабочей станции** и нажмите кнопку **Дальше**.  
  
4.  На странице **Мастер установки SQL Server** нажмите кнопку **Далее**.  
  
5.  На странице **Проверка конфигурации системы** нажмите кнопку **Далее**.  
  
6.  В окне **Изменить или удалить экземпляр** выберите **Изменить установленные компоненты**.  
  
7.  В окне **Выбор компонентов** раскройте узел **Документация, примеры и образцы баз данных**.  
  
8.  Выберите **Образцы кода и приложений**.  Выберите **Образцы баз данных**, затем образец базы данных для удаления и выберите **Компонент станет недоступным**.  Нажмите кнопку **Далее**.  
  
9. Нажмите кнопку **Установить** и завершите мастер установки.  
  
#### Присоединение файлов образца базы данных AdventureWorks к SQL Server  
  
1.  После загрузки файла установщика образца базы данных дважды щелкните **AdventureWorksDB.msi** \(или другой загруженный файл\), чтобы установить базу данных.  По умолчанию база данных устанавливается в папку c:\\Program Files\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data.  
  
2.  Подключите файлы базы данных AdventureWorks к экземпляру SQL Server, выполнив следующий скрипт в командной строке SQLCMD или в среде SQL Server Management Studio:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Если файлы были установлены на другой диск или в другой каталог, нужно исправить соответствующие пути перед выполнением хранимой процедуры `sp_attach_db`.  
  
## Загрузка SQL Server Express Edition  
 В образцах и пошаговых руководствах раздела [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] в качестве хранилища данных используется SQL Server 2005, но их можно изменить, чтобы использовать SQL Server Express Edition.  SQL Server Express Edition доступен бесплатно и его можно распространять вместе с приложениями.  Если используется среда [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], то SQL Server Express входит в состав выпуска Pro и выпусков с более широкими возможностями.  
  
#### Загрузка и установка выпуска SQL Server Express  
  
1.  Запустите Internet Explorer.  
  
2.  Перейдите на страницу загрузки [Microsoft SQL Server 2005, экспресс\-выпуск](http://go.microsoft.com/fwlink/?LinkID=31070).  
  
3.  Следуйте указаниям по установке, содержащимся на веб\-узле.  
  
## См. также  
 [Приступая к работе](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)