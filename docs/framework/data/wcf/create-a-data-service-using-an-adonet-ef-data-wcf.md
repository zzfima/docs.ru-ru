---
title: "Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d69a3cf60b60806085a9bb7ae292cc88ba99871e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляет данные сущности в виде службы данных. Эти данные сущностей предоставляются [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], если источником данных является реляционная база данных. В этом разделе будет показано создание модели данных на базе [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] в веб-приложении [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], основанном на существующей базе данных, а также создание новой службы данных с помощью этой модели.  
  
 Кроме того, в составе [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] предусмотрена программа командной строки, которая может создавать модель [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] за пределами проекта [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Добавление модели Entity Framework на основе существующей базы данных в существующее веб-приложение  
  
1.  На **проекта** меню, нажмите кнопку **добавить новый элемент**.  
  
2.  В **шаблоны** области, нажмите кнопку **данные** категории, а затем выберите **ADO.NET Entity Data Model**.  
  
3.  Введите имя модели и нажмите кнопку **добавить**.  
  
     Отображается первая страница мастера [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
4.  В **Выбор содержимого модели** выберите **создать из базы данных**. Затем нажмите кнопку **Далее**.  
  
5.  Нажмите кнопку **новое подключение** кнопки.  
  
6.  В **свойства соединения** диалоговое окно, введите имя сервера, выберите метод проверки подлинности, введите имя базы данных и нажмите кнопку **ОК**.  
  
     **Выбор подключения к данным**диалогового обновляется параметры подключения к базе данных.  
  
7.  Убедитесь, что **сохранить настройки подключения сущности в App.Config как:** установлен флажок. Затем нажмите кнопку **Далее**.  
  
8.  В **Выбор объектов базы данных** диалоговое окно, выберите все объекты базы данных, которые планируется предоставлять в службе данных.  
  
    > [!NOTE]
    >  Объекты, включенные в модель данных, не предоставляются службой данных автоматически. Они должны явно предоставляться самой службой. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
9. Нажмите кнопку **Готово** для завершения работы мастера.  
  
     При этом создается модель данных по умолчанию на основе указанной базы данных. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] позволяет настроить модель данных. Дополнительные сведения см. в разделе [Задачи](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Создание службы данных с использованием новой модели данных  
  
1.  В [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] откройте EDMX-файл, представляющий модель данных.  
  
2.  В **браузер моделей**, щелкните правой кнопкой мыши модель, нажмите кнопку **свойства**и запишите имя контейнера сущностей.  
  
3.  В **обозревателе решений**, щелкните правой кнопкой мыши имя вашего [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента**.  
  
4.  В **Добавление нового элемента** выберите **службы данных WCF**.  
  
5.  Задайте имя для службы и нажмите кнопку **ОК**.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] создает метку XML и файлы с кодом для новой службы. По умолчанию открывается окно редактора кода.  
  
6.  В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом, порожденным от класса <xref:System.Data.Objects.ObjectContext> и являющимся контейнером сущностей модели данных, который был отмечен на шаге 2.  
  
7.  Включите в коде службы данных доступ авторизованных клиентов к наборам сущностей, предоставляемым службой данных. Дополнительные сведения см. в разделе [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
8.  Для тестирования службы Northwind.svc данных с помощью веб-браузера, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>См. также  
 [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Как: создание службы данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Как: создание службы данных с использованием LINQ к источнику данных SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
