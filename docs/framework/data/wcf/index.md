---
title: Службы WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 6910bfbc94f69292bb8c2a52bf3ebef8fcfb3a8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876464"
---
# <a name="wcf-data-services-45"></a>Службы WCF Data Services 4.5

Службы WCF Data Services (прежнее название «Службы данных ADO.NET») — это компонент платформы .NET Framework, которая позволяет создавать службы, использующие [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для предоставления и получения данных через Интернет или интрасеть с помощью семантики [ передачи репрезентативного состояния (REST)](https://go.microsoft.com/fwlink/?LinkId=113919). OData предоставляет доступ к данным в виде ресурсов, которые адресуются по URI. Доступ и изменение данных производится с помощью таких стандартных команд HTTP, как GET, PUT, POST и DELETE. OData использует правила сущность связь [модели EDM](../../../../docs/framework/data/adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных ассоциациями.

Службы WCF Data Services использует протокол OData для адресации и обновлении ресурсов. Таким образом доступ к этим службам из любого клиента, поддерживающего OData. OData позволяет запрашивать и записывать данные в ресурсы с использованием традиционных форматов передачи: Atom, набора стандартов обмена и обновления данных XML и нотации объектов JavaScript (JSON), формат текстовых данных exchange, применяемого в приложениях AJAX.

Службы WCF Data Services позволяет предоставлять данные, поступающие из различных источников, как веб-каналов OData. Набор средств Visual Studio упрощают создание службы на основе OData с помощью модели данных ADO.NET Entity Framework. Можно также создать веб-каналов OData на основе классы CLR (CLR) и даже с поздним связыванием или нетипизированных данных.

Службы WCF Data Services также включает набор клиентских библиотек: одну для типовых клиентских приложений .NET Framework, а другую специально для приложений на основе Silverlight. Эти клиентские библиотеки предоставляют модель объектно ориентированного программирования, при доступе к каналу OData из среды, например .NET Framework и Silverlight.

## <a name="where-should-i-start"></a>Подготовка к изучению темы

В зависимости от потребностей рассмотрите возможность Приступая к работе со службами данных WCF в одном из следующих разделов.

Необходимо перейти непосредственно к…

- [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

- [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

- [Краткое руководство по Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Краткое руководство по Silverlight для разработчиков Windows Phone](https://go.microsoft.com/fwlink/?LinkID=214535)

Просто Ознакомьте меня примерами кода...

- [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

- [Практическое руководство. Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

- [Практическое руководство. Привязка данных к элементам Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

Я хочу узнать больше о OData...

- [Технический документ. Введение в OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Веб-сайт протокола Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

- [OData: ПАКЕТ SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

- [OData: Вопросы и ответы](https://go.microsoft.com/fwlink/?LinkId=185867)

Я хочу посмотреть некоторые видеоматериалы...

- [Руководство для начинающих по службам данных WCF](https://go.microsoft.com/fwlink/?LinkId=220864)

- [Видеофильмы о службах данных WCF для разработчиков](https://go.microsoft.com/fwlink/?LinkId=220861)

- [OData: Веб-узел разработчиков](https://go.microsoft.com/fwlink/?LinkId=185866)

Я хочу см. в разделе примеров end-to-end...

- [Образцы документации по службам WCF Data Services в коллекции образцов MSDN](https://go.microsoft.com/fwlink/?LinkID=220865)

- [Другие образцы служб WCF Data Services в коллекции образцов MSDN](https://go.microsoft.com/fwlink/?LinkId=220866)

- [OData: ПАКЕТ SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

Как происходит интеграция со средствами Visual Studio

- [Создание библиотеки клиентов службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

- [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md)

- [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

Рекомендуемые действия в этой ситуации

- [Обзор](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

- [Технический документ. Введение в OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Сценарии приложения](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

Я хочу использовать Silverlight...

- [Краткое руководство по Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Службы WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Приступая к работе с Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Я хочу использовать LINQ...

- [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

- [Рекомендации по LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

- [Практическое руководство. Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

Я по-прежнему требуются некоторые дополнительные сведения...

- [Блог группы служб WCF Data Services](https://go.microsoft.com/fwlink/?LinkID=150511)

- [Ресурсы](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

- [Центр разработчиков WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Веб-сайт протокола Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>В этом разделе

[Обзор](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

Обзор возможностей и функций, доступных в службах WCF Data Services.

[Новые возможности в службах WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Описывает новые возможности в службах WCF Data Services и поддержка новых функций OData.

[Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

Описывает предоставление и использование веб-каналов OData с помощью служб данных WCF.

[Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

Описывает создание и настройка службы данных, которая предоставляет веб-каналов OData.

[Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

Описывает использование клиентских библиотек для использования каналов OData из клиентского приложения .NET Framework.

## <a name="see-also"></a>См. также

- [Передача состояния представления (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
