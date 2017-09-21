---
title: "Службы WCF Data Services 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- HTML
- VB
- CSharp
- C++
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b491d644112137cb24e847439aa133691e5261d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/05/2017

---
# <a name="wcf-data-services-45"></a>Службы WCF Data Services 4.5
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] (которые раньше назывались ADO.NET Data Services) — это компонент платформы .NET Framework, с помощью которого можно создавать службы, использующие [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для передачи и получения данных через Интернет или интрасеть с помощью семантики [REST](http://go.microsoft.com/fwlink/?LinkId=113919). Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставляют данные как ресурсы, адресуемые с помощью URI. Доступ и изменение данных производится с помощью таких стандартных команд HTTP, как GET, PUT, POST и DELETE. В службах [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] используются соглашения об отношениях сущностей из [модели EDM](../../../../docs/framework/data/adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных сопоставлениями.  
  
 При адресации и обновлении ресурсов службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] используют протокол [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. В результате доступ к этим службам можно получить из любого клиента, который поддерживает [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] позволяет осуществлять запросы и запись данных в ресурсы с использованием традиционных форматов передачи: Atom, набора стандартов обмена и обновления данных на основе XML и нотации объектов JavaScript (JSON), текстового формата обмена данными, широко применяемого в приложениях AJAX.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет предоставлять данные, поступающие из различных источников, в виде каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Средства Visual Studio упрощают создание служб на базе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] за счет использования модели данных ADO.NET Entity Framework. Также можно создавать каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], основанные на классах CLR, данных с поздним связыванием или данных, не имеющих типа.  
  
 В состав служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] также включен набор клиентских библиотек: одна для типовых клиентских приложений .NET Framework, а другая специально для приложений на основе Silverlight. Данные клиентской библиотеки предоставляют возможности объектно ориентированного программирования для доступа к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из таких платформ, как .NET Framework и Silverlight.  
  
## <a name="where-should-i-start"></a>Подготовка к изучению темы  
 В зависимости от потребностей, ознакомьтесь с началом работы со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в одном из следующих разделов.  
  
 Необходимо перейти непосредственно к…  
 -   [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [Краткое руководство по Silverlight](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [Краткое руководство по Silverlight для разработчиков Windows Phone](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 Просто ознакомьте меня с примерами кода…  
 -   [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Практическое руководство. Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [Практическое руководство. Привязка данных к элементам Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 Требуются дополнительные сведения о [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…  
 -   [Технический документ. Введение в OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Веб-сайт протокола Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [OData: часто задаваемые вопросы](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 Хочу посмотреть некоторые видеоматериалы…  
 -   [Руководство для начинающих по службам данных WCF](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [Видеофильмы о службах данных WCF для разработчиков](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [OData: веб-сайт разработчиков](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 Требуются комплексные образцы  
 -   [Образцы документации по службам WCF Data Services в коллекции образцов MSDN](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [Другие образцы служб WCF Data Services в коллекции образцов MSDN](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 Как происходит интеграция со средствами Visual Studio  
 -   [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 Рекомендуемые действия в этой ситуации  
 -   [Обзор набора средств Visual Studio для Unity](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [Технический документ. Введение в OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Сценарии приложения](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 Необходима информация об использовании Silverlight…  
 -   [Краткое руководство по Silverlight](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [Службы WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [Приступая к работе с Silverlight](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 Я хочу создать приложение Windows Phone…  
 -   [Краткое руководство по Silverlight для разработчиков Windows Phone](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [Клиент протокола OData для Windows Phone](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 Сведения об использовании LINQ…  
 -   [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [Рекомендации по LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [Практическое руководство. Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 Необходимы дополнительные сведения...  
 -   [Блог группы служб WCF Data Services](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [Ресурсы](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [Центр разработчиков WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [Веб-сайт протокола Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a>Содержание  
 [Обзор набора средств Visual Studio для Unity](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 Содержит общие сведения о функциях и возможностях, доступных в службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [Новые возможности служб данных WCF](http://msdn.microsoft.com/en-us/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 Описывает новые возможности в службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] и поддержку новых возможностей [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 Описывает предоставление и получение каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 Описывает создание и настройку службы данных, предоставляющей каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 Описывает использование клиентских библиотек для использования канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из клиентского приложения .NET Framework.  
  
## <a name="see-also"></a>См. также  
 [Передача состояния представления (REST)](http://go.microsoft.com/fwlink/?LinkId=113919)

