---
title: Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 4bccd1e4655786ae24166cdc32619b420c4a54d3
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743778"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)

Службы данных WCF предоставляет данные сущности в виде службы данных. Эти данные сущностей предоставляется [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] когда источником данных является реляционной базы данных. В этом разделе показано, как создать [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-на основе модели данных в Visual Studio веб-приложения, основанную на существующей базы данных и использовать эту модель данных для создания новой службы данных.

[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Также предоставляет средство командной строки, позволяющее создать [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] модели за пределами проекта Visual Studio. Дополнительные сведения см. в разделе [как: использование EdmGen.exe для формирования модели и сопоставления файлов](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Добавление модели Entity Framework на основе существующей базы данных в существующее веб-приложение

1. На **проекта** меню, щелкните **добавить** > **новый элемент**.

2. В **шаблоны** панели щелкните **данных** категории, а затем выберите **ADO.NET Entity Data Model**.

3. Введите имя модели и нажмите кнопку **добавить**.

     Отображается первая страница мастера [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].

4. В **Выбор содержимого модели** выберите **создать из базы данных**. Затем нажмите кнопку **Далее**.

5. Нажмите кнопку **новое подключение** кнопки.

6. В **свойства соединения** диалоговом окне введите имя сервера, выберите метод проверки подлинности, введите имя базы данных и нажмите кнопку **ОК**.

     **Выбор подключения к данным** диалоговое окно обновляется параметры подключения к базе данных.

7. Убедитесь, что **сохранить настройки подключения сущности в App.Config как:** флажок. Затем нажмите кнопку **Далее**.

8. В **Choose Your Database Objects** диалоговое окно, выберите все объекты базы данных, которые планируется предоставлять в службе данных.

    > [!NOTE]
    > Объекты, включенные в модель данных, не предоставляются службой данных автоматически. Они должны явно предоставляться самой службой. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

9. Нажмите кнопку **Готово** завершите работу мастера.

     При этом создается модель данных по умолчанию на основе указанной базы данных. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] позволяет настроить модель данных. Дополнительные сведения см. в разделе [Задачи](https://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Создание службы данных с использованием новой модели данных

1. Откройте в Visual Studio файл EDMX, представляющий модель данных.

2. В **браузер моделей**, щелкните правой кнопкой мыши модель, нажмите кнопку **свойства**и запишите имя контейнера сущностей.

3. В **обозревателе решений**, щелкните правой кнопкой мыши имя вашего [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **добавить** > **новый элемент**.

4. В **Добавление нового элемента** выберите **WCF-сервиса данных** шаблона в **Web** категории.

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > **WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.

5. Укажите имя для службы и нажмите кнопку **ОК**.

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода.

6. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом, порожденным от класса <xref:System.Data.Objects.ObjectContext> и являющимся контейнером сущностей модели данных, который был отмечен на шаге 2.

7. Включите в коде службы данных доступ авторизованных клиентов к наборам сущностей, предоставляемым службой данных. Дополнительные сведения см. в разделе [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).

8. Чтобы проверить службы данных Northwind.svc с помощью веб-браузер, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>См. также

- [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Практическое руководство. Создание службы данных с использованием поставщика отражений](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)