---
title: 'Как: доступ к объектам стандартных UTC и местным временем зоны'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7ddf7ba69d8bed84f62d329fd26794e2641d954
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="c0f75-102">Как: доступ к объектам стандартных UTC и местным временем зоны</span><span class="sxs-lookup"><span data-stu-id="c0f75-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="c0f75-103"><xref:System.TimeZoneInfo> Класс содержит два свойства <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A>, что предоставляете доступ кода к предопределенных объекта часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="c0f75-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="c0f75-104">В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.</span><span class="sxs-lookup"><span data-stu-id="c0f75-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="c0f75-105">Получение объекта TimeZoneInfo времени UTC</span><span class="sxs-lookup"><span data-stu-id="c0f75-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="c0f75-106">Используйте `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство для доступа к в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="c0f75-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="c0f75-107">Вместо назначения <xref:System.TimeZoneInfo> объекты, возвращаемые этим свойством переменной объекта продолжать обращаться к Гринвичу через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="c0f75-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="c0f75-108">Получение местного часового пояса</span><span class="sxs-lookup"><span data-stu-id="c0f75-108">To access the local time zone</span></span>

1. <span data-ttu-id="c0f75-109">Используйте `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство для доступа к локальной системе часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="c0f75-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="c0f75-110">Вместо назначения <xref:System.TimeZoneInfo> объекты, возвращаемые этим свойством переменной объекта продолжать обращаться к местного часового пояса через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="c0f75-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="c0f75-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c0f75-111">Example</span></span>

<span data-ttu-id="c0f75-112">В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.</span><span class="sxs-lookup"><span data-stu-id="c0f75-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="c0f75-113">Следует всегда обращаться к местного часового пояса через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство вместо назначения местное время зона на <xref:System.TimeZoneInfo> объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="c0f75-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="c0f75-114">Аналогичным образом, следует всегда обращаться к Гринвичу через <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> свойство вместо назначения в формате UTC зона на <xref:System.TimeZoneInfo> объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="c0f75-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="c0f75-115">Это предотвращает <xref:System.TimeZoneInfo> объектной переменной с помощью вызова недопустимого <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="c0f75-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c0f75-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c0f75-116">Compiling the code</span></span>

<span data-ttu-id="c0f75-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c0f75-117">This example requires:</span></span>

* <span data-ttu-id="c0f75-118">Чтобы ссылка на System.Core.dll была добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="c0f75-118">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="c0f75-119">Что <xref:System> импортировать пространство имен с `using` инструкции (обязательно в коде C#).</span><span class="sxs-lookup"><span data-stu-id="c0f75-119">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0f75-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c0f75-120">See also</span></span>

<span data-ttu-id="c0f75-121">[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[поиск часового пояса, определенные в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[как: создание объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span><span class="sxs-lookup"><span data-stu-id="c0f75-121">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span></span>
