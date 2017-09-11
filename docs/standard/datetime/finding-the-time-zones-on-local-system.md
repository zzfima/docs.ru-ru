---
title: "Поиск часового пояса, заданного в локальной системе"
description: "Поиск часового пояса, заданного в локальной системе"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e61017e2a0e26295c3be7e8265674b1a5d2ae5a3
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="677df-104">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="677df-104">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="677df-105">Класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) не предоставляет открытый конструктор.</span><span class="sxs-lookup"><span data-stu-id="677df-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not expose a public constructor.</span></span> <span data-ttu-id="677df-106">В результате ключевое слово `new` невозможно использовать для создания нового объекта [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="677df-106">As a result, the `new` keyword cannot be used to create a new [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="677df-107">Вместо этого экземпляры объектов [TimeZoneInfo](xref:System.TimeZoneInfo) создаются путем извлечения информации о предопределенных часовых поясах из реестра.</span><span class="sxs-lookup"><span data-stu-id="677df-107">Instead, [TimeZoneInfo](xref:System.TimeZoneInfo) objects are instantiated by retrieving information on predefined time zones from the operating system.</span></span> <span data-ttu-id="677df-108">В этом разделе описывается создание экземпляра часового пояса из данных, хранимых в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="677df-108">This topic discusses instantiating a time zone from data stored by the operating system.</span></span> <span data-ttu-id="677df-109">Кроме того, свойства `static` (`Shared` в Visual Basic) класса [TimeZoneInfo](xref:System.TimeZoneInfo) предоставляют доступ к часовому поясу UTC и местному часовому поясу.</span><span class="sxs-lookup"><span data-stu-id="677df-109">In addition, `static` (`Shared` in Visual Basic) properties of the [TimeZoneInfo](xref:System.TimeZoneInfo) class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="677df-110">Доступ к отдельным часовым поясам</span><span class="sxs-lookup"><span data-stu-id="677df-110">Accessing Individual Time Zones</span></span>

<span data-ttu-id="677df-111">Класс [TimeZoneInfo](xref:System.TimeZoneInfo) предоставляет два предопределенных объекта часовых поясов, которые представляют собой время UTC и местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="677df-111">The [TimeZoneInfo](xref:System.TimeZoneInfo) class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="677df-112">Они доступны из свойств [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) и [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) соответственно.</span><span class="sxs-lookup"><span data-stu-id="677df-112">They are available from the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) and [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) properties, respectively.</span></span> <span data-ttu-id="677df-113">Инструкции по доступу к часовому поясу UTC или местному часовому поясу см. в разделе [Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов](access-utc-and-local.md).</span><span class="sxs-lookup"><span data-stu-id="677df-113">For instructions on accessing the UTC or local time zones, see [How to: access the predefined UTC and local time zone objects](access-utc-and-local.md).</span></span> 

<span data-ttu-id="677df-114">Можно также создать экземпляр объекта [TimeZoneInfo](xref:System.TimeZoneInfo), который представляет любой часовой пояс, определенный в реестре.</span><span class="sxs-lookup"><span data-stu-id="677df-114">You can also instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents any time zone defined by the operating system.</span></span> <span data-ttu-id="677df-115">Инструкции по созданию экземпляра объекта конкретного часового пояса см. в разделе [Практическое руководство. Создание экземпляра объекта TimeZoneInfo.](instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="677df-115">For instructions on instantiating a specific time zone object, see [How to: instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="677df-116">Идентификаторы часовых поясов</span><span class="sxs-lookup"><span data-stu-id="677df-116">Time Zone Identifiers</span></span>

<span data-ttu-id="677df-117">Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="677df-117">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="677df-118">Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный.</span><span class="sxs-lookup"><span data-stu-id="677df-118">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="677df-119">В большинстве случаев его значение соответствует свойству [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName), которое используется для предоставления имени стандартному времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="677df-119">In most cases, its value corresponds to the [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="677df-120">Однако существуют исключения.</span><span class="sxs-lookup"><span data-stu-id="677df-120">However, there are exceptions.</span></span> <span data-ttu-id="677df-121">Лучшим способом убедиться, что предоставлен действительный идентификатор, является выполнение перечисления доступных в системе часовых поясов и отслеживание связанных с ними идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="677df-121">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span> <span data-ttu-id="677df-122">Инструкции по перечислению часовых поясов см. в разделе [Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="677df-122">For instructions on enumerating time zones, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="677df-123">См. также</span><span class="sxs-lookup"><span data-stu-id="677df-123">See Also</span></span>

[<span data-ttu-id="677df-124">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="677df-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="677df-125">Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов</span><span class="sxs-lookup"><span data-stu-id="677df-125">How to: access the predefined UTC and local time zone objects</span></span>](access-utc-and-local.md)

[<span data-ttu-id="677df-126">Практическое руководство. Создание экземпляра объекта TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="677df-126">How to: instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)

[<span data-ttu-id="677df-127">Практическое руководство. Перечисление присутствующих на компьютере часовых поясов</span><span class="sxs-lookup"><span data-stu-id="677df-127">How to: enumerate time zones present on a computer</span></span>](enumerate-time-zones.md)

[<span data-ttu-id="677df-128">Преобразование времени из одного часового пояса в другой</span><span class="sxs-lookup"><span data-stu-id="677df-128">Converting times between time zones</span></span>](converting-between-time-zones.md)
