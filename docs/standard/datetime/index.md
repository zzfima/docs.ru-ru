---
title: "Даты, время и часовые пояса"
description: "Даты, время и часовые пояса"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 76e6cacc-1c0c-4a71-8cb8-018c112385ba
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: a4d0a68ac32c3d722a1479ca2b067892fd88bf52

---

# <a name="dates-times-and-time-zones"></a>Даты, время и часовые пояса

В дополнение к основной структуре [System.DateTime](xref:System.DateTime), платформа .NET предоставляет следующие классы, которые поддерживают работу с часовыми поясами:

* [System.TimeZoneInfo](xref:System.TimeZoneInfo)
    
  Этот класс используется для работы с локальным часовым поясом и с временем в формате UTC.
  
* [System.DateTimeOffset](xref:System.DateTimeOffset)  

  Эта структура используется для работы с датами и временем, чье смещение (или различие) от времени в формате UTC известно. Структура [DateTimeOffset](xref:System.DateTimeOffset) объединяет значение даты и времени со смещением этого времени от времени в формате UTC. Благодаря связи со временем в формате UTC отдельное значение даты и времени однозначно идентифицирует единственный момент времени. Это делает значение [DateTimeOffset](xref:System.DateTimeOffset) более пригодным для переноса с одного компьютера на другой, чем значение [DateTime](xref:System.DateTime). 
  
Этот раздел документации содержит сведения, необходимые для работы с часовыми поясами и создания приложений, поддерживающих часовые пояса и способных преобразовывать дату и время из одного часового пояса в другой.

## <a name="in-this-section"></a>Содержание

[Общие сведения о часовых поясах](time-zone-overview.md): описание терминологии, основных понятий и вопросов, связанных с созданием приложений, поддерживающих часовые пояса.
    
[Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](choosing-between-datetime.md): объясняется, в каких случаях следует использовать типы [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset) и [System.TimeZoneInfo](xref:System.TimeZoneInfo) при работе с данными даты и времени.
    
[Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md): описание способов перечисления часовых поясов, находящихся в локальной системе.

[Создание экземпляра объекта DateTimeOffset](instantiating-a-datetimeoffset-object.md): описание способов, с помощью которых можно создать экземпляр объекта [System.DateTimeOffset](xref:System.DateTimeOffset) и преобразовать значение [System.DateTime](xref:System.DateTime) в значение [System.DateTimeOffset](xref:System.DateTimeOffset).

[Выполнение арифметических операций с датами и временем](performing-arithmetic-operations.md): обзор вопросов, связанных со сложением, вычитанием и сравнением значений [System.DateTime](xref:System.DateTime) и [System.DateTimeOffset](xref:System.DateTimeOffset).

[Взаимное преобразование структур DateTime и DateTimeOffset](converting-between-datetime-and-offset.md): описание преобразований между значениями [System.DateTime](xref:System.DateTime) и [System.DateTimeOffset](xref:System.DateTimeOffset).

[Преобразование времени из одного часового пояса в другой](converting-between-time-zones.md): описание способов преобразования времени из одного часового пояса в другой.

[Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](enumerate-time-zones.md): примеры, в которых перечисляются часовые пояса, определенные в реестре компьютера, а пользователям предоставляется возможность выбрать предопределенный часовой пояс из списка.

[Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов](access-utc-and-local.md): описание способов доступа к времени в формате UTC и к локальному часовому поясу.

[Практическое руководство. Создание экземпляра объекта TimeZoneInfo](instantiate-time-zone-info.md): описание способов создания экземпляра объекта [System.TimeZoneInfo](xref:System.TimeZoneInfo) из локального системного реестра.

[Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](use-time-zones-in-arithmetic.md): описание способов выполнения арифметических действий с датами и временем, которые отражают правила коррекции часовых поясов.

[Практическое руководство. Разрешение проблемы неоднозначности времени](resolve-ambiguous-times.md): сведения об устранении неоднозначного времени с помощью его сопоставления часовому поясу стандартного времени.

[Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени](let-users-resolve-ambiguous-times.md): сведения о том, как позволить пользователю определять сопоставление между неоднозначными местным временем и временем в формате UTC.

## <a name="reference"></a>Ссылка

[System.TimeZoneInfo](xref:System.TimeZoneInfo)

[System.DateTimeOffset](xref:System.DateTimeOffset)

[System.DateTime](xref:System.DateTime)



<!--HONumber=Nov16_HO1-->


