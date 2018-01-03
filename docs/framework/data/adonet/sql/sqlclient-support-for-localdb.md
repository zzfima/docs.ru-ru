---
title: "Поддержка SqlClient LocalDB"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: "14"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 99845420549393829582ade11f38b75e3ebff484
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-support-for-localdb"></a>Поддержка SqlClient LocalDB
Начиная с версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] с кодовым наименованием Denali, будет доступна упрощенная версия [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], именуемая LocalDB. В этом разделе описывается, как установить подключение к базе данных LocalDB.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о LocalDB, включая установку и настройку экземпляра LocalDB, см. в электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] .  
  
 Обзор возможностей LocalDB:  
  
-   Создание и запуск экземпляров LocalDB через sqllocaldb.exe или файл app.config.  
  
-   Использование sqlcmd.exe для добавления и изменения базы данных в экземпляре LocalDB. Например, `sqlcmd -S (localdb)\myinst`.  
  
-   Чтобы добавить базу данных к своему экземпляру LocalDB, пользуйтесь ключевым словом строки подключения `AttachDBFilename` . Если при использовании `AttachDBFilename`не указано имя базы данных ключевым словом строки подключения `Database` , то база данных удаляется из экземпляра LocalDB после завершения работы приложения.  
  
-   Укажите экземпляр LocalDB в строке подключения. Например, если экземпляр имеет имя `myInstance`, то строка подключения включает следующее:  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 Указание`User Instance=True` недопустимо, если производится соединение с базой данных LocalDB.  
  
 Базу данных LocalDB можно скачать из [пакета дополнительных компонентов Microsoft SQL Server 2012](http://www.microsoft.com/download/en/details.aspx?id=29065). Если необходимо изменение данных в экземпляре LocalDB с помощью программы sqlcmd.exe, то необходимо пользоваться версией sqlcmd из [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012. Эту программу можно также получить из пакета дополнительных компонентов [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012.  
  
## <a name="programmatically-create-a-named-instance"></a>Создание именованного экземпляра программным путем  
 В приложении можно создать именованный экземпляр и определить базу данных следующим образом.  
  
-   Определите создаваемые экземпляры LocalDB в файле app.config, как показано ниже.  Номер версии экземпляра должен совпадать с номером версии установки LocalDB.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   Укажите имя экземпляра с помощью ключевого слова строки подключения `server` .  Имя экземпляра, указанное в ключевом слове строки подключения `server` , должно соответствовать имени, указанному в файле app.config.  
  
-   С помощью ключевого слова строки подключения `AttachDBFilename` укажите MDF-файл.  
  
## <a name="see-also"></a>См. также  
 [Возможности SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
