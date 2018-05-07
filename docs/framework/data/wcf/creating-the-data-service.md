---
title: Создание службы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: bb6e2f7c1160fa51cd897cc953ad0ed721559294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-data-service"></a>Создание службы данных
В этой задаче вы создадите образца службы данных, который использует [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для предоставления [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] канала, который основан на образце базы данных "Борей". Задача включает следующие основные шаги.  
  
1.  Создайте веб-приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
2.  Определите модель данных с помощью средств [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
3.  Добавление службы данных в веб-приложение.  
  
4.  Включите доступ к службе данных.  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Выполняется веб-приложение, создаваемое после завершения этой задачи [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , предоставляемые Visual Studio Development Server. Сервер разработки [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поддерживает доступ только с локального компьютера. Чтобы упростить тестирование и устранение неполадок службы данных в ходе разработки, попробуйте также запустить с помощью IIS приложение со службой данных. Для получения дополнительной информации см. [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
### <a name="to-create-the-aspnet-web-application"></a>Создание веб-приложения ASP.NET  
  
1.  В Visual Studio на **файл** выберите пункт **New**, а затем выберите **проекта**.  
  
2.  В **новый проект** в поле выберите Visual Basic или Visual C# **Web** шаблона, а затем выберите **веб-приложение ASP.NET**.  
  
    > [!NOTE]
    >  Если используется среда Visual Studio Web Developer, то вместо нового веб-приложения нужно будет создать новый веб-сайт.  
  
3.  Тип `NorthwindService` как имя проекта.  
  
4.  Нажмите кнопку **ОК**.  
  
5.  (Необязательно) Укажите конкретный номер порта для веб-приложения. Примечание. В оставшейся части этого краткого руководства используется номер порта `12345`.  
  
    1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта только что создан и нажмите кнопку **свойства**.  
  
    2.  Выберите **Web** и задайте значение **определенный порт** текстового поля, чтобы `12345`.  
  
### <a name="to-define-the-data-model"></a>Определение модели данных  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента.**  
  
2.  В **Добавление нового элемента** диалоговое окно, нажмите кнопку **данные** шаблона, а затем выберите **ADO.NET Entity Data Model**.  
  
3.  Введите имя модели данных, `Northwind.edmx`.  
  
4.  В [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] мастера выберите **создать из базы данных**, а затем нажмите кнопку **Далее**.  
  
5.  Подключите модель данных в базу данных, выполнив одно из следующих действий и нажмите кнопку **Далее**:  
  
    -   Если нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создать новое соединение. Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631). Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.  
  
         \- или -  
  
    -   Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.  
  
6.  На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.  
  
7.  Нажмите кнопку **Готово** для завершения работы мастера.  
  
    > [!NOTE]
    >  Эта сформированная модель данных предоставляет свойства внешнего ключа для типов сущности. Модели данных, созданные с помощью Visual Studio 2008, не включают эти свойства внешнего ключа. В связи с этим перед получением доступа к этой версии службы данных Northwind необходимо обновить клиентские классы службы данных любого клиентского приложения для доступа к службе данных, созданного с помощью среды Visual Studio 2008.  
  
### <a name="to-create-the-data-service"></a>Создание службы данных  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя вашего [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента**.  
  
2.  В **Добавление нового элемента** выберите **службы данных WCF**.  
  
3.  Имя службы, введите `Northwind`.  
  
     Visual StudioVisual Studio создает файлы разметки и кодов XML для новой службы. По умолчанию открывается окно редактора кода. В **обозревателе решений**, для службы будет отображаться имя Northwind с расширением. svc.cs или. svc.vb.  
  
4.  В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a>Включение доступа к ресурсам службы данных  
  
1.  В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.  
  
    > [!NOTE]
    >  Клиент, пытающийся получить доступ к приложению [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], может также получить доступ к источникам, представляемым службой данных. Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения. Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="next-steps"></a>Следующие шаги  
 Успешно создана новая служба данных, которая предоставляет [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канала, который основан на базе данных Northwind и включен доступ к потоку для клиентов, имеющих разрешения на [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-приложения. Теперь запустим эту службу данных из среды Visual Studio и обратимся к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью запросов HTTP GET через веб-браузер.  
  
 [Доступ к службе из веб-браузера](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>См. также  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
