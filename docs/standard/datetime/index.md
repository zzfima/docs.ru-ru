---
title: "Даты, время и часовые пояса"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 47681f129c428cdae2be5e493fc6ac31719cab28
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dates-times-and-time-zones"></a>Даты, время и часовые пояса

В дополнение к основной структуре <xref:System.DateTime> платформа .NET предоставляет следующие классы, которые поддерживают работу с часовыми поясами.

* <xref:System.TimeZone>

  Этот класс используется для работы с системным локальным часовым поясом и временем в формате UTC. Функциональные возможности класса <xref:System.TimeZone> во многом замещены возможностями класса <xref:System.TimeZoneInfo>.

* <xref:System.TimeZoneInfo>

  Этот класс используется для работы с любым часовым поясом, который является стандартным в системе, для создания новых часовых поясов и для быстрого преобразования значений даты и времени из одного часового пояса в другой. При разработке нового решения используйте класс <xref:System.TimeZoneInfo> вместо класса <xref:System.TimeZone>.

* <xref:System.DateTimeOffset>

  Эта структура используется для работы с датами и временем, чье смещение (или различие) от времени в формате UTC известно. Структура <xref:System.DateTimeOffset> объединяет значение даты и времени со смещением этого времени от времени в формате UTC. Благодаря связи со временем в формате UTC отдельное значение даты и времени однозначно идентифицирует единственный момент времени. Это делает значение <xref:System.DateTimeOffset> более пригодным для переноса с одного компьютера на другой, чем значение <xref:System.DateTime>.

Этот раздел документации содержит сведения, необходимые для работы с часовыми поясами и создания приложений, поддерживающих часовые пояса и способных преобразовывать дату и время из одного часового пояса в другой.

## <a name="in-this-section"></a>Содержание раздела

[Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md). Описание терминологии, основных понятий и вопросов, связанных с созданием приложений, поддерживающих часовые пояса.

[Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md). Объясняется, в каких случаях следует использовать типы <xref:System.DateTime>, <xref:System.DateTimeOffset> и <xref:System.TimeZoneInfo> при работе с данными даты и времени.

[Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md). Описание того, как перечислять часовые пояса, находящиеся в локальной системе.

[Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](../../../docs/standard/datetime/enumerate-time-zones.md). Примеры, в которых перечисляются часовые пояса, определенные в реестре компьютера, и которые предоставляют пользователям возможность выбрать предопределенный часовой пояс из списка.

[Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов](../../../docs/standard/datetime/access-utc-and-local.md). Описание способов доступа ко времени в формате UTC и локальному часовому поясу.

[Практическое руководство. Создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md). Описание способов создания экземпляра объекта <xref:System.TimeZoneInfo> из локального системного реестра.

[Создание экземпляра объекта DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md). Описание способов, с помощью которых можно создать экземпляр объекта <xref:System.DateTimeOffset> и преобразовать значение <xref:System.DateTime> в значение <xref:System.DateTimeOffset>.

[Практическое руководство. Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md). Описание того, как можно создать пользовательский часовой пояс, который не поддерживает переход на летнее время и обратно.

[Практическое руководство. Создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md). Описание того, как можно создать пользовательский часовой пояс, который поддерживает переход на летнее время и обратно.

[Сохранение и восстановление часовых поясов](../../../docs/standard/datetime/saving-and-restoring-time-zones.md). Описание сериализации и десериализации данных часового пояса в <xref:System.TimeZoneInfo> и демонстрация некоторых сценариев, в которых эти функции могут использоваться.

[Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md). Описание того, как создать пользовательский часовой пояс и сохранить связанные сведения в файле ресурсов.

[Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md). Описание того, как восстановить пользовательский часовой пояс, сохраненный в файл ресурсов.

[Выполнение арифметических операций с датами и временем](../../../docs/standard/datetime/performing-arithmetic-operations.md). Обзор вопросов, связанных со сложением, вычитанием и сравнением значений <xref:System.DateTime> и <xref:System.DateTimeOffset>.

[Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md). Описание того, как выполнять с датами и временем арифметические действия, которые отражают правила коррекции часовых поясов.

[Взаимное преобразование структур DateTime и DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md). Описание преобразований между значениями <xref:System.DateTime> и <xref:System.DateTimeOffset>.

[Преобразование времени из одного часового пояса в другой](../../../docs/standard/datetime/converting-between-time-zones.md). Описание того, как преобразовать время из одного часового пояса в другой.

[Практическое руководство. Разрешение проблемы неоднозначности времени](../../../docs/standard/datetime/resolve-ambiguous-times.md). Сведения об устранении неоднозначного времени с помощью его сопоставления с часовым поясом стандартного времени.

[Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md). Сведения о том, как позволить пользователю определять сопоставление между неоднозначными местным временем и временем в формате UTC.

## <a name="reference"></a>Ссылка

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
