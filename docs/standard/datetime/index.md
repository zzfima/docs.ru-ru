---
title: Даты, время и часовые пояса
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a5594b689a52b641ecece0f9a92fb6cdfe5735
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991284"
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="3e2f0-102">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="3e2f0-102">Dates, times, and time zones</span></span>

<span data-ttu-id="3e2f0-103">В дополнение к основной структуре <xref:System.DateTime> платформа .NET предоставляет следующие классы, которые поддерживают работу с часовыми поясами.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="3e2f0-104">Этот класс используется для работы с локальным часовым поясом и с временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.</span></span> <span data-ttu-id="3e2f0-105">Функциональные возможности <xref:System.TimeZone> класса в основном заменяются <xref:System.TimeZoneInfo> классом.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-105">The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="3e2f0-106">Этот класс используется для работы с любым часовым поясом, который является стандартным в системе, для создания новых часовых поясов и для быстрого преобразования значений даты и времени из одного часового пояса в другой.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-106">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="3e2f0-107">При разработке нового решения используйте класс <xref:System.TimeZoneInfo> вместо класса <xref:System.TimeZone>.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-107">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="3e2f0-108">Эта структура используется для работы с датами и временем, чье смещение (или различие) от времени в формате UTC известно.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-108">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="3e2f0-109">Структура <xref:System.DateTimeOffset> объединяет значение даты и времени со смещением этого времени от времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-109">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="3e2f0-110">Благодаря связи со временем в формате UTC отдельное значение даты и времени однозначно идентифицирует единственный момент времени.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-110">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="3e2f0-111">Это делает значение <xref:System.DateTimeOffset> более пригодным для переноса с одного компьютера на другой, чем значение <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-111">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="3e2f0-112">Этот раздел документации содержит сведения, необходимые для работы с часовыми поясами и создания приложений, поддерживающих часовые пояса и способных преобразовывать дату и время из одного часового пояса в другой.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-112">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3e2f0-113">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="3e2f0-113">In this section</span></span>

<span data-ttu-id="3e2f0-114">[Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md). Описание терминологии, основных понятий и вопросов, связанных с созданием приложений, поддерживающих часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-114">[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="3e2f0-115">[Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md). Объясняется, в каких случаях следует использовать типы <xref:System.DateTime>, <xref:System.DateTimeOffset> и <xref:System.TimeZoneInfo> при работе с данными даты и времени.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-115">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="3e2f0-116">[Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md). Описание того, как перечислять часовые пояса, находящиеся в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-116">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="3e2f0-117">[Практическое руководство. Перечисление часовых поясов, имеющихся](../../../docs/standard/datetime/enumerate-time-zones.md) на компьютере, содержит примеры, которые перечисляют Часовые пояса, определенные в реестре компьютера, и позволяющие пользователям выбрать предопределенный часовой пояс из списка.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-117">[How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="3e2f0-118">[Практическое руководство. Доступ к стандартным объектам](../../../docs/standard/datetime/access-utc-and-local.md) времени в формате UTC и местному часовому поясу описывается, как получить доступ к всеобщему скоординированному времени и местному часовому поясу.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-118">[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="3e2f0-119">[Практическое руководство. Создание экземпляра объекта](../../../docs/standard/datetime/instantiate-time-zone-info.md) TimeZoneInfo описывает, как создать экземпляр <xref:System.TimeZoneInfo> объекта из локального системного реестра.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-119">[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="3e2f0-120">[Создание экземпляра объекта DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md). Описание способов, с помощью которых можно создать экземпляр объекта <xref:System.DateTimeOffset> и преобразовать значение <xref:System.DateTime> в значение <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-120">[Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="3e2f0-121">[Практическое руководство. Создание часовых поясов без правил](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) коррекции описывает создание настраиваемого часового пояса, который не поддерживает переход на летнее время и обратно.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-121">[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="3e2f0-122">[Практическое руководство. Создание часовых поясов с правилами](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) коррекции описывает создание настраиваемого часового пояса, поддерживающего один или несколько переходов на летнее время и обратно.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-122">[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="3e2f0-123">[Сохранение и восстановление часовых поясов](../../../docs/standard/datetime/saving-and-restoring-time-zones.md). Описание сериализации и десериализации данных часового пояса в <xref:System.TimeZoneInfo> и демонстрация некоторых сценариев, в которых эти функции могут использоваться.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-123">[Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="3e2f0-124">[Практическое руководство. Экономия часовых поясов во внедренном](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) ресурсе описывается создание пользовательского часового пояса и сохранение его данных в файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-124">[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="3e2f0-125">[Практическое руководство. Восстановление часовых поясов из внедренного](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) ресурса описывает, как создать экземпляры пользовательских часовых поясов, сохраненных во внедренном файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-125">[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="3e2f0-126">[Выполнение арифметических операций с датами и временем](../../../docs/standard/datetime/performing-arithmetic-operations.md). Обзор вопросов, связанных со сложением, вычитанием и сравнением значений <xref:System.DateTime> и <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-126">[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="3e2f0-127">[Практическое руководство. Использование часовых поясов в арифметике](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) даты и времени обсуждаются способы выполнения арифметических действий с датами и временем, отражающими правила коррекции часового пояса.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-127">[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="3e2f0-128">[Взаимное преобразование структур DateTime и DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md). Описание преобразований между значениями <xref:System.DateTime> и <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-128">[Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="3e2f0-129">[Преобразование времени из одного часового пояса в другой](../../../docs/standard/datetime/converting-between-time-zones.md). Описание того, как преобразовать время из одного часового пояса в другой.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-129">[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="3e2f0-130">[Практическое руководство. Устранение неоднозначных](../../../docs/standard/datetime/resolve-ambiguous-times.md) времени. описывает, как устранить неоднозначное время, сопоставив его со стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-130">[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="3e2f0-131">[Практическое руководство. Разрешить пользователям неоднозначное](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) время указывает, как разрешить пользователю определять сопоставление между неоднозначным местным временем и временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3e2f0-131">[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="3e2f0-132">Ссылка</span><span class="sxs-lookup"><span data-stu-id="3e2f0-132">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
