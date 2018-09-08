---
title: Как разработать службу данных WCF Data Service, работающую на IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: af81e65dfd4661d62d7aa4a3e6075be312765cb7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185445"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Практическое: разработке службы данных WCF, выполняющегося на сервере IIS

В этом разделе показано, как использовать службы данных WCF для создания службы данных, основанный на образце базы данных "Борей", которая размещена в веб-приложения ASP.NET, на котором выполняется на Internet Information Services (IIS). Пример создания службы данных Northwind в качестве веб-приложения ASP.NET, выполняющегося на сервере разработки ASP.NET, см. в разделе [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

> [!NOTE]
> Для создания службы данных Northwind необходимо установить образец базы данных Northwind на локальный компьютер. Чтобы скачать этот образец базы данных, см. на странице загрузки [образцы баз данных для SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).

 Данный раздел иллюстрирует создание службы данных с помощью поставщика Entity Framework. Доступны другие поставщики служб данных. Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).

 После создания службы требуется явно предоставить доступ к ресурсам службы данных. Дополнительные сведения см. в разделе [как: разрешить доступ к службе данных](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Создание веб-приложение ASP.NET, который выполняется на IIS

1. В Visual Studio на **файл** меню, выберите **New** > **проекта**.

2. В **новый проект** выберите **установленные** > [**Visual C#** или **Visual Basic**] > **Web** категории.

3. Выберите **веб-приложение ASP.NET** шаблона.

1. Введите `NorthwindService` как имя проекта.

5. Нажмите кнопку **ОК**.

6. На **проекта** меню, выберите **свойства службы Northwind**.

7. Выберите **Web** , а затем выберите **использовать локальный веб-сервер IIS**.

8. Нажмите кнопку **создать виртуальный каталог** и нажмите кнопку **ОК**.

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

    1. Откройте диспетчер IIS и перейдите в приложение PhotoService на **веб-сайт по умолчанию**.

    2. В **Просмотр возможностей**, дважды щелкните **проверки подлинности**.

    3. На **проверки подлинности** выберите **анонимную проверку подлинности**.

    4. В **действия** панели щелкните **изменить** Чтобы задать участника безопасности, в разделе которого анонимные пользователи будут подключаться к сайту.

    5. В **изменение учетных данных анонимной проверки подлинности** выберите **удостоверение пула приложений**.

    > [!IMPORTANT]
    > При использовании учетной записи сетевой службы анонимным пользователям предоставляется доступ к внутренней сети, связанной с этой учетной записью.

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

## <a name="define-the-data-model"></a>Определение модели данных

1. В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.

2. В **Добавление нового элемента** выберите **ADO.NET Entity Data Model**.

3. Введите имя модели данных, `Northwind.edmx`.

4. В мастере модели EDM выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.

5. Подключите модель данных в базу данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**:

    -   Если у вас нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создайте новое соединение. Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](https://go.microsoft.com/fwlink/?LinkId=123631). Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.

         \- или -

    -   Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.

6. На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.

7. Нажмите кнопку **Готово** чтобы закрыть мастер.

## <a name="create-the-data-service"></a>Создание службы данных

1. В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.

2. В **Добавление нового элемента** выберите **WCF-сервиса данных**.

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > **WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.

3. Имя службы, введите `Northwind`.

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **обозревателе решений**, служба имеет имя, Northwind и расширение. svc.cs или. svc.vb.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>См. также

- [Предоставление данных как службы](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
