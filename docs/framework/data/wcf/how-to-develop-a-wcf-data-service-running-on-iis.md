---
title: "Как разработать службу данных WCF Data Service, работающую на IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6ba18a1823386042a3aaf61cffac357871eca294
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Как разработать службу данных WCF Data Service, работающую на IIS
В этом разделе показано, как использовать [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для создания службы данных, основанный на образце базы данных Northwind, размещенное на веб-приложения ASP.NET, на котором работает в Internet Information Services (IIS). Пример создания службы данных Northwind в виде веб-приложения ASP.NET, работающая на сервере разработки ASP.NET см. в разделе [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
> [!NOTE]
>  Для создания службы данных Northwind необходимо установить образец базы данных Northwind на локальный компьютер. Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).  
  
 Данный раздел иллюстрирует создание службы данных с помощью поставщика Entity Framework. Доступны другие поставщики служб данных. Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
 После создания службы требуется явно предоставить доступ к ресурсам службы данных. Дополнительные сведения см. в разделе [как: разрешить доступ к службе данных](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a>Создание веб-приложения ASP.NET, работающего на базе IIS  
  
1.  В Visual Studio на **файл** выберите пункт **New**, а затем выберите **проекта**.  
  
2.  В **новый проект** диалогового окна выберите Visual Basic или Visual C# в качестве языка программирования.  
  
3.  В **шаблоны** выберите **веб-приложение ASP.NET**. Примечание. Если используется среда Visual Studio Web Developer, то вместо нового веб-приложения нужно будет создать новый веб-узел.  
  
4.  Тип `NorthwindService` как имя проекта.  
  
5.  Нажмите кнопку **ОК**.  
  
6.  На **проекта** последовательно выберите пункты **свойства службы Northwind**.  
  
7.  Выберите **Web** , а затем выберите **использовать локальный веб-сервер IIS**.  
  
8.  Нажмите кнопку **создать виртуальный каталог** и нажмите кнопку **ОК**.  
  
9. С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).  
  
    -   32-разрядные системы:  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   64-разрядные системы:  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     Она регистрирует Windows Communication Foundation (WCF) на компьютере.  
  
10. С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).  
  
    -   32-разрядные системы:  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   64-разрядные системы:  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     Это необходимо для того, чтобы проверить правильность работы служб IIS после установки WCF на компьютере. Возможно, потребуется перезапустить службы IIS.  
  
11. Если приложение ASP.NET запущено в службах IIS7, нужно также выполнить следующие действия.  
  
    1.  Откройте диспетчер служб IIS и перейдите в приложение PhotoService на **веб-сайт по умолчанию**.  
  
    2.  В **Просмотр возможностей**, дважды щелкните **проверки подлинности**.  
  
    3.  На **проверки подлинности** выберите **анонимную проверку подлинности**.  
  
    4.  В **действия** области, нажмите кнопку **изменить** Чтобы задать участника безопасности, в области которого анонимные пользователи будут подключаться к сайту.  
  
    5.  В **изменение учетных данных анонимной проверки подлинности** выберите **удостоверение пула приложений**.  
  
    > [!IMPORTANT]
    >  При использовании учетной записи сетевой службы анонимным пользователям предоставляется доступ к внутренней сети, связанной с этой учетной записью.  
  
12. С помощью среды SQL Server Management Studio, программы sqlcmd.exe или редактора Transact-SQL в Visual Studio выполните следующую команду Transact-SQL для экземпляра SQL Server с прикрепленной базой данных Northwind.  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     Она создает имя входа в экземпляр SQL Server для учетной записи Windows, используемой для запуска служб IIS. Это позволит службам IIS подключиться к экземпляру SQL Server.  
  
13. После присоединения базы данных Northwind выполните следующие команды Transact-SQL:  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     Они предоставляют право на новое имя входа, позволяющее службам IIS читать данные из базы данных Northwind и записывать данные в эту базу данных.  
  
### <a name="to-define-the-data-model"></a>Определение модели данных  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавление нового элемента.**  
  
2.  В **Добавление нового элемента** выберите **ADO.NET Entity Data Model**.  
  
3.  Введите имя модели данных, `Northwind.edmx`.  
  
4.  В мастера модели EDM, выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.  
  
5.  Подключите модель данных в базу данных, выполнив одно из следующих действий и нажмите кнопку **Далее**:  
  
    -   Если нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создать новое соединение. Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631). Этот экземпляр [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] должен содержать присоединенный образец базы данных Northwind.  
  
         \- или -  
  
    -   Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.  
  
6.  На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.  
  
7.  Нажмите кнопку **Готово** для завершения работы мастера.  
  
    > [!NOTE]
    >  Эта сформированная модель данных предоставляет свойства внешнего ключа для типов сущности. Модели данных, созданные с помощью Visual Studio 2008, не включают эти свойства внешнего ключа. В связи с этим перед получением доступа к этой версии службы данных Northwind необходимо обновить клиентские классы службы данных любого клиентского приложения для доступа к службе данных, созданного с помощью среды Visual Studio 2008.  
  
### <a name="to-create-the-data-service"></a>Создание службы данных  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавление нового элемента**.  
  
2.  В **Добавление нового элемента** выберите **службы данных ADO.NET**.  
  
3.  Имя службы, введите `Northwind`.  
  
     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **обозревателе решений**, для службы будет отображаться имя Northwind с расширением. svc.cs или. svc.vb.  
  
4.  В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a>См. также  
 [Предоставление данных как службы](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
