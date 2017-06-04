---
title: "Создание службы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Создание службы данных
В этой задаче создается образец службы данных, в котором используется [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для обеспечения доступа к каналу [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], который основан на образце базы данных Борей. Задача включает следующие основные шаги:  
  
1.  Создайте веб\-приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
2.  Определите модель данных с помощью средств [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
3.  Добавление службы данных в веб\-приложение.  
  
4.  Включите доступ к службе данных.  
  
> [!NOTE]
>  Веб\-приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], создаваемое в конце этой задачи, работает на сервере разработки [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], предоставляемом [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  Сервер разработки [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поддерживает доступ только с локального компьютера.  Чтобы упростить тестирование и устранение неполадок службы данных в ходе разработки, попробуйте также запустить с помощью IIS приложение со службой данных.  Для получения дополнительной информации см. [Как разработать службу данных WCF Data Service, работающую на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
### Создание веб\-приложения ASP.NET  
  
1.  В [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] меню **Файл** выберите **Создать** и щелкните пункт **Проект**.  
  
2.  В диалоговом окне **Создание проекта** на вкладке [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] выберите **Веб**\-шаблон, затем выберите **Веб\-приложение ASP.NET**.  
  
    > [!NOTE]
    >  При использовании [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer следует создавать новый узел вместо нового веб\-приложения.  
  
3.  Введите `NorthwindService` в качестве названия проекта.  
  
4.  Нажмите кнопку **ОК**.  
  
5.  \(Необязательно\) Укажите конкретный номер порта для веб\-приложения.  Примечание. В оставшейся части этого краткого руководства используется номер порта `12345`.  
  
    1.  В **Обозревателе решений** щелкните правой кнопкой мыши имя созданного проекта [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и выберите пункт **Свойства**.  
  
    2.  Выберите вкладку **Веб** и задайте в текстовом поле **Определенный порт** значение `12345`.  
  
### Определение модели данных  
  
1.  В **Обозревателе решений** щелкните правой кнопкой мыши имя проекта [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и выберите **Добавить новый элемент**.  
  
2.  В диалоговом окне **Добавление нового элемента** щелкните шаблон **Данные** и **Модель EDM ADO.NET**.  
  
3.  В качестве имени модели данных введите `Northwind.edmx`.  
  
4.  В мастере [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] выберите **Создать из базы данных** и нажмите кнопку **Далее**.  
  
5.  Подключите модель данных к базе данных, выполнив одно из следующих действий, и затем нажмите кнопку **Далее**.  
  
    -   При отсутствии уже настроенного подключения к базе данных выберите пункт **Создать подключение** и создайте новое подключение.  Дополнительные сведения см. в разделе [Практическое руководство. Создание подключения к базам данных SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631).  Этот экземпляр [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] должен содержать присоединенный образец базы данных Northwind.  
  
         \-или\-  
  
    -   Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.  
  
6.  На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.  
  
7.  Чтобы закрыть мастер, нажмите кнопку **Готово**.  
  
    > [!NOTE]
    >  Эта сформированная модель данных предоставляет свойства внешнего ключа для типов сущности.  Модели данных, создаваемые с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008, не содержат свойств внешнего ключа.  Поэтому, прежде чем пытаться получить доступ к этой версии службы данных Northwind, необходимо обновить классы службы данных клиентских приложений, созданных для доступа к службе данных Northwind, которая была создана с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008.  
  
### Создание службы данных  
  
1.  В **Обозревателе решений** щелкните правой кнопкой мыши имя проекта [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и выберите **Добавить новый элемент**.  
  
2.  В диалоговом окне **Добавление нового элемента** выберите пункт **Служба данных WCF**.  
  
3.  В качестве имени службы укажите `Northwind`.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]В Visual Studio для новой службы создаются файлы разметки и кодов XML.  По умолчанию открывается окно редактора кода.  В **обозревателе решений** для службы будет отображаться имя Northwind с расширением .svc.cs или .svc.vb.  
  
4.  В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`.  Определение класса должно выглядеть следующим образом.  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### Включение доступа к ресурсам службы данных  
  
1.  В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.  
  
    > [!NOTE]
    >  Клиент, пытающийся получить доступ к приложению [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], может также получить доступ к источникам, представляемым службой данных.  Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения.  Для получения дополнительной информации см. [Защита служб WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## Следующие действия  
 Новая служба данных, представляющая поток [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], успешно создана, она основывается на образце базы данных Northwind. Доступ к потоку для клиентов, имеющих права для веб\-приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], включен.  Далее служба данных будет запущена из [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], и доступ к потоку [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] будет получен путем отправки запросов HTTP GET через веб\-браузер.  
  
 [Доступ к службе из веб\-браузера](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## См. также  
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ru-ru/91076853-0881-421b-837a-f582f36be527)