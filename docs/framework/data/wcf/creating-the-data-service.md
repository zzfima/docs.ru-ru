---
title: "Создание службы данных"
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
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 37d32d938f49d0767594e0f141d5a463ad5fc95f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="creating-the-data-service"></a>Создание службы данных
В этой задаче вы создадите образца службы данных, который использует [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для предоставления [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] канала, который основан на образце базы данных "Борей". Задача включает следующие основные шаги.  
  
1.  Создайте веб-приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
2.  Определите модель данных с помощью средств [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
3.  Добавление службы данных в веб-приложение.  
  
4.  Включите доступ к службе данных.  
  
> [!NOTE]
>  Веб-приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], создаваемое в конце этой задачи, работает на сервере разработки [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], предоставляемом [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Сервер разработки [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поддерживает доступ только с локального компьютера. Чтобы упростить тестирование и устранение неполадок службы данных в ходе разработки, попробуйте также запустить с помощью IIS приложение со службой данных. Для получения дополнительной информации см. [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
### <a name="to-create-the-aspnet-web-application"></a>Создание веб-приложения ASP.NET  
  
1.  В [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]на **файл** последовательно выберите пункты **New**, а затем выберите **проекта**.  
  
2.  В **новый проект** в поле либо [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] выберите **Web** шаблона, а затем выберите **веб-приложение ASP.NET**.  
  
    > [!NOTE]
    >  При использовании [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer следует создавать новый узел вместо нового веб-приложения.  
  
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
  
    -   Если нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создать новое соединение. Дополнительные сведения см. в разделе [как: создание подключений к базам данных SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631). Этот экземпляр [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] должен содержать присоединенный образец базы данных Northwind.  
  
         \- или -  
  
    -   Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.  
  
6.  На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.  
  
7.  Нажмите кнопку **Готово** для завершения работы мастера.  
  
    > [!NOTE]
    >  Эта сформированная модель данных предоставляет свойства внешнего ключа для типов сущности. Модели данных, создаваемые с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008, не содержат свойств внешнего ключа. Поэтому, прежде чем пытаться получить доступ к этой версии службы данных Northwind, необходимо обновить классы службы данных клиентских приложений, созданных для доступа к службе данных Northwind, которая была создана с помощью [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008.  
  
### <a name="to-create-the-data-service"></a>Создание службы данных  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя вашего [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] проекта, а затем нажмите кнопку **Добавление нового элемента**.  
  
2.  В **Добавление нового элемента** выберите **службы данных WCF**.  
  
3.  Имя службы, введите `Northwind`.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **обозревателе решений**, для службы будет отображаться имя Northwind с расширением. svc.cs или. svc.vb.  
  
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
  
## <a name="next-steps"></a>Дальнейшие действия  
 Успешно создана новая служба данных, которая предоставляет [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канала, который основан на базе данных Northwind и включен доступ к потоку для клиентов, имеющих разрешения на [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-приложения. Далее будет запущена служба данных из [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] и получают доступ к [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала, отправляя запросы HTTP GET через веб-браузер:  
  
 [Доступ к службе из веб-браузера](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>См. также  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
