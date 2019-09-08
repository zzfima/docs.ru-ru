---
title: Службы WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 017fe2177cf824d461b4c51ea805f75b6ddbe064
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779986"
---
# <a name="wcf-data-services-45"></a>Службы WCF Data Services 4.5

WCF Data Services (прежнее название — "службы данных ADO.NET") — это компонент .NET Framework, который позволяет создавать службы, использующие [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для предоставления и использования данных в Интернете или интрасети с помощью семантики [состояния представления. Перемещение (остальное)](https://go.microsoft.com/fwlink/?LinkId=113919). OData предоставляет доступ к данным в виде ресурсов, которые адресуются по URI. Доступ и изменение данных производится с помощью таких стандартных команд HTTP, как GET, PUT, POST и DELETE. OData использует соглашения об отношениях отношений сущностей [EDM](../adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных ассоциациями.

WCF Data Services использует протокол OData для адресации и обновления ресурсов. Таким образом, доступ к этим службам можно получить с любого клиента, поддерживающего OData. OData позволяет запрашивать и записывать данные в ресурсы с помощью хорошо известных форматов перемещения: Atom, набор стандартов для обмена и обновления данных в формате XML и нотация объектов JavaScript (JSON), текстовый формат обмена данными, широко применяемый в приложениях AJAX.

WCF Data Services может предоставлять данные, происходящие из различных источников, в качестве каналов OData. Средства Visual Studio облегчают создание службы на основе OData с помощью модели данных ADO.NET Entity Framework. Можно также создавать веб-каналы OData на основе классов среды CLR и даже данных с поздним связыванием или нетипизированными данными.

WCF Data Services также включает набор клиентских библиотек, один для общих .NET Framework клиентских приложений и другой специально для приложений на основе Silverlight. Эти клиентские библиотеки предоставляют модель программирования на основе объектов при доступе к каналу OData из таких сред, как .NET Framework и Silverlight.

## <a name="where-should-i-start"></a>Подготовка к изучению темы

В зависимости от ваших интересов рекомендуется приступить к работе с WCF Data Services в одном из следующих разделов.

Необходимо перейти непосредственно к…

- [Краткое руководство](quickstart-wcf-data-services.md)

- [Начало работы](getting-started-with-wcf-data-services.md)

- [Краткое руководство по Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Краткое руководство по Silverlight для разработчиков Windows Phone](https://go.microsoft.com/fwlink/?LinkID=214535)

Просто покажите мне код...

- [Краткое руководство](quickstart-wcf-data-services.md)

- [Практическое руководство. Выполнение запросов службы данных](how-to-execute-data-service-queries-wcf-data-services.md)

- [Практическое руководство. Привязка данных к Windows Presentation Foundation элементам](bind-data-to-wpf-elements-wcf-data-services.md)

Я хочу узнать больше о OData...

- [Технический документ Знакомство с OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Веб-сайт протокола Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

- [Протокола TOOL](https://go.microsoft.com/fwlink/?LinkID=185248)

- [Протокола Вопросы и ответы](https://go.microsoft.com/fwlink/?LinkId=185867)

Я хочу посмотреть некоторые видео...

- [Руководство для начинающих по службам данных WCF](https://go.microsoft.com/fwlink/?LinkId=220864)

- [Видеофильмы о службах данных WCF для разработчиков](https://go.microsoft.com/fwlink/?LinkId=220861)

- [Протокола Веб-сайт разработчиков](https://go.microsoft.com/fwlink/?LinkId=185866)

Я хочу просмотреть полный пример...

- [Образцы документации по службам WCF Data Services в коллекции образцов MSDN](https://go.microsoft.com/fwlink/?LinkID=220865)

- [Другие образцы служб WCF Data Services в коллекции образцов MSDN](https://go.microsoft.com/fwlink/?LinkId=220866)

- [Протокола TOOL](https://go.microsoft.com/fwlink/?LinkID=185248)

Как происходит интеграция со средствами Visual Studio

- [Создание библиотеки клиентов службы данных](generating-the-data-service-client-library-wcf-data-services.md)

- [Создание службы данных](creating-the-data-service.md)

- [Поставщик Entity Framework](entity-framework-provider-wcf-data-services.md)

Рекомендуемые действия в этой ситуации

- [Обзор](wcf-data-services-overview.md)

- [Технический документ Знакомство с OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Сценарии приложения](application-scenarios-wcf-data-services.md)

Я хочу использовать Silverlight...

- [Краткое руководство по Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Службы WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Приступая к работе с Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Я хочу использовать LINQ...

- [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)

- [Рекомендации по LINQ](linq-considerations-wcf-data-services.md)

- [Практическое руководство. Выполнение запросов службы данных](how-to-execute-data-service-queries-wcf-data-services.md)

Мне по-прежнему нужны дополнительные сведения...

- [Блог группы служб WCF Data Services](https://go.microsoft.com/fwlink/?LinkID=150511)

- [Ресурсы](wcf-data-services-resources.md)

- [Центр разработчиков WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Веб-сайт протокола Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>В этом разделе

[Обзор](wcf-data-services-overview.md)

Содержит общие сведения о функциях и функциях, доступных в WCF Data Services.

[Новые возможности WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Описание новых функциональных возможностей WCF Data Services и поддержки новых функций OData.

[Начало работы](getting-started-with-wcf-data-services.md)

Описывает, как предоставлять и использовать каналы OData с помощью WCF Data Services.

[Определение служб данных WCF](defining-wcf-data-services.md)

Описывает создание и настройку службы данных, предоставляющей доступ к каналам OData.

[Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)

Описывает использование клиентских библиотек для использования каналов OData из клиентского приложения .NET Framework.

## <a name="see-also"></a>См. также

- [Передача состояния представления (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
