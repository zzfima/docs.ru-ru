---
title: Как выполнить Создание часовых поясов без правил коррекции
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3ffc7b6f1f7baec7ce6beb5a50b706ff78bfa1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681720"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="4d356-102">Как выполнить Создание часовых поясов без правил коррекции</span><span class="sxs-lookup"><span data-stu-id="4d356-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="4d356-103">Точные сведения о часовом поясе, которые требуются для приложения может отсутствовать в конкретной системе по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="4d356-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="4d356-104">Часовой пояс никогда не был определен в локального системного реестра.</span><span class="sxs-lookup"><span data-stu-id="4d356-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="4d356-105">Данные о часовом поясе, изменен или удален из реестра.</span><span class="sxs-lookup"><span data-stu-id="4d356-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="4d356-106">Часовой пояс существует, но не поддерживает точные сведения о коррекции часового пояса для конкретного исторического периода.</span><span class="sxs-lookup"><span data-stu-id="4d356-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="4d356-107">В этих случаях можно вызвать <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод для определения часового пояса, необходимой для приложения.</span><span class="sxs-lookup"><span data-stu-id="4d356-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="4d356-108">Можно использовать перегрузки этого метода, создаваемого с или без правил коррекции часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="4d356-109">Если часовой пояс поддерживает летнее время, можно определить с помощью либо правила коррекции fixed или с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="4d356-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="4d356-110">(Для определения этих терминов см. в разделе «Терминология часовых поясов» в [Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="4d356-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d356-111">Пользовательский часовой пояс, созданных вызывающими <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод не добавляются в реестр.</span><span class="sxs-lookup"><span data-stu-id="4d356-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="4d356-112">Вместо этого они может осуществляться только через ссылку на объект, возвращаемый <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> вызова метода.</span><span class="sxs-lookup"><span data-stu-id="4d356-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="4d356-113">В этом разделе показано создание часовых поясов без правил коррекции.</span><span class="sxs-lookup"><span data-stu-id="4d356-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="4d356-114">Чтобы создать часовой пояс, который поддерживает правил коррекции летнего времени, см. в разделе [как: Создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="4d356-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="4d356-115">Создание часовых поясов без правил коррекции</span><span class="sxs-lookup"><span data-stu-id="4d356-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="4d356-116">Определите отображаемое имя часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="4d356-117">Отображаемое имя соответствует стандартному формату, в котором смещение часового пояса от времени в формате UTC, заключенный в круглые скобки и сопровождается строку, которая определяет часовой пояс, один или несколько городов в часовой пояс, или один или несколько из частей в курс заданий или области в часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="4d356-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="4d356-118">Определите имя для зимнего времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="4d356-119">Как правило эта строка также используется как идентификатор часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="4d356-120">Если вы хотите использовать другой идентификатор, чем стандартное имя часового пояса, определите идентификатор часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="4d356-121">Создать экземпляр <xref:System.TimeSpan> объект, который определяет смещение часового пояса от времени UTC.</span><span class="sxs-lookup"><span data-stu-id="4d356-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="4d356-122">Часовые пояса со временем, которые прибыли позже, чем UTC, имеют положительное смещение.</span><span class="sxs-lookup"><span data-stu-id="4d356-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="4d356-123">Часовые пояса со временем, предшествующих UTC, имеют отрицательное смещение.</span><span class="sxs-lookup"><span data-stu-id="4d356-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="4d356-124">Вызовите <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> метод для создания экземпляра нового часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="4d356-125">Пример</span><span class="sxs-lookup"><span data-stu-id="4d356-125">Example</span></span>

<span data-ttu-id="4d356-126">В следующем примере определяется пользовательский часовой пояс для Моусон, Антарктика, который без правил коррекции.</span><span class="sxs-lookup"><span data-stu-id="4d356-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="4d356-127">Строкой, назначенной <xref:System.TimeZoneInfo.DisplayName%2A> свойство осуществляется согласно стандартному формату, в котором смещение часового пояса от времени UTC сопровождается понятное описание часового пояса.</span><span class="sxs-lookup"><span data-stu-id="4d356-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="4d356-128">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4d356-128">Compiling the code</span></span>

<span data-ttu-id="4d356-129">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="4d356-129">This example requires:</span></span>

* <span data-ttu-id="4d356-130">Чтобы добавить в проект ссылку на библиотеку System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="4d356-130">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="4d356-131">Что импортируется следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="4d356-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="4d356-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4d356-132">See also</span></span>

- [<span data-ttu-id="4d356-133">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="4d356-133">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="4d356-134">Общие сведения о часовых поясах</span><span class="sxs-lookup"><span data-stu-id="4d356-134">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="4d356-135">Практическое руководство. Создание часовых поясов с правилами коррекции</span><span class="sxs-lookup"><span data-stu-id="4d356-135">How to: Create time zones with adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
