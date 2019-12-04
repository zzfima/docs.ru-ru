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
ms.openlocfilehash: 684361dbb97e70296a3061f71102662023f88d9a
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800513"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Руководство. Разработка службы данных WCF, работающей на сервере IIS

В этом разделе показано, как использовать WCF Data Services для создания службы данных, основанной на образце базы данных Northwind, которая размещена в веб-приложении ASP.NET, работающем на службы IIS (IIS). Пример создания одной и той же службы данных Northwind как веб-приложения ASP.NET, выполняемого на ASP.NET Development Server, см. в [кратком руководстве по WCF Data Services](quickstart-wcf-data-services.md).

> [!NOTE]
> Для создания службы данных Northwind необходимо установить образец базы данных Northwind на локальный компьютер. Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).

Данный раздел иллюстрирует создание службы данных с помощью поставщика Entity Framework. Доступны другие поставщики служб данных. Дополнительные сведения см. в разделе [поставщики служб данных](data-services-providers-wcf-data-services.md).

После создания службы требуется явно предоставить доступ к ресурсам службы данных. Дополнительные сведения см. [в разделе инструкции. Включение доступа к службе данных](how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Создание веб-приложения ASP.NET, которое выполняется в службах IIS

1. В Visual Studio в меню **Файл** выберите пункты **Создать** > **Проект**.

2. В диалоговом окне **Новый проект** выберите **установленный** > [**Visual C#**  или **Visual Basic**] > **веб-** категорию.

3. Выберите шаблон **Веб-приложение ASP.NET** .

4. Введите `NorthwindService` в качестве имени проекта.

5. Нажмите кнопку **ОК**.

6. В меню **проект** выберите **Свойства норсвиндсервице**.

7. Перейдите на вкладку **веб** , а затем выберите **использовать локальный веб-сервер IIS**.

8. Щелкните **создать виртуальный каталог** , а затем нажмите кнопку **ОК**.

9. С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).

    - Для 32-разрядных систем:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - 64-разрядные системы:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     Она регистрирует Windows Communication Foundation (WCF) на компьютере.

10. С помощью командной строки с правами администратора выполните одну из следующих команд (в зависимости от операционной системы).

    - Для 32-разрядных систем:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - 64-разрядные системы:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     Это необходимо для того, чтобы проверить правильность работы служб IIS после установки WCF на компьютере. Возможно, потребуется перезапустить службы IIS.

11. Если приложение ASP.NET запущено в службах IIS7, нужно также выполнить следующие действия.

    1. Откройте диспетчер IIS и перейдите к приложению службы приложений на **веб-сайте по умолчанию**.

    2. В окне **Просмотр возможностей** дважды щелкните элемент **Проверка подлинности**.

    3. На странице **Проверка подлинности** выберите **Анонимная проверка подлинности**.

    4. На панели **действия** нажмите кнопку **изменить** , чтобы задать субъект безопасности, в котором анонимные пользователи будут подключаться к сайту.

    5. В диалоговом окне **изменение учетных данных анонимной проверки подлинности** выберите **удостоверение пула приложений**.

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

1. В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить** > **новый элемент**.

2. В диалоговом окне **Добавление нового элемента** выберите **ADO.NET EDM**.

3. В качестве имени модели данных введите `Northwind.edmx`.

4. В мастере EDM выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.

5. Подключите модель данных к базе данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**.

    - Если подключение к базе данных уже не настроено, щелкните **создать соединение** и создайте новое соединение. Дополнительные сведения см. в разделе [How to: Create Connections to SQL Server Databases](https://go.microsoft.com/fwlink/?LinkId=123631). Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.

         \- или -

    - Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.

6. На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.

7. Чтобы закрыть мастер, нажмите кнопку **Готово**.

## <a name="create-the-data-service"></a>Создание службы данных

1. В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить** > **новый элемент**.

2. В диалоговом окне **Добавление нового элемента** выберите **WCF Data Service**.

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Шаблон **службы данных WCF** доступен в visual Studio 2015, но не в visual Studio 2017 или более поздней версии.

3. В качестве имени службы введите `Northwind`.

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **Обозреватель решений**служба имеет имя, Northwind и расширение. svc.cs или. svc. vb.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>См. также:

- [Предоставление данных как службы](exposing-your-data-as-a-service-wcf-data-services.md)
