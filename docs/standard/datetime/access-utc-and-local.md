---
title: Как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу
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
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132604"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="7e1cc-102">Как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу</span><span class="sxs-lookup"><span data-stu-id="7e1cc-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="7e1cc-103">Класс <xref:System.TimeZoneInfo> предоставляет два свойства: <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A>, которые предоставляют коду доступ к предопределенным объектам часового пояса.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="7e1cc-104">В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="7e1cc-105">Получение объекта TimeZoneInfo времени UTC</span><span class="sxs-lookup"><span data-stu-id="7e1cc-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="7e1cc-106">Для доступа к всеобщему скоординированному времени используйте свойство `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="7e1cc-107">Вместо того, чтобы назначать объект <xref:System.TimeZoneInfo>, возвращаемый свойством, в объектную переменную, продолжайте обращаться к времени в формате UTC через свойство <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="7e1cc-108">Получение местного часового пояса</span><span class="sxs-lookup"><span data-stu-id="7e1cc-108">To access the local time zone</span></span>

1. <span data-ttu-id="7e1cc-109">Используйте свойство `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> для доступа к часовому поясу локальной системы.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="7e1cc-110">Вместо того чтобы назначать объект <xref:System.TimeZoneInfo>, возвращаемый свойством, в объектную переменную, продолжайте обращаться к местному часовому поясу через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="7e1cc-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7e1cc-111">Example</span></span>

<span data-ttu-id="7e1cc-112">В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="7e1cc-113">Необходимо всегда обращаться к локальному часовому поясу через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>, а не назначать местный часовой пояс переменной объекта <xref:System.TimeZoneInfo>.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="7e1cc-114">Аналогичным образом следует всегда обращаться к всеобщему скоординированному времени через свойство <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>, а не назначать часовой пояс в <xref:System.TimeZoneInfo> объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="7e1cc-115">Это предотвращает невозможность сделать недействительным <xref:System.TimeZoneInfo>ную переменную объекта при вызове метода <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e1cc-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="7e1cc-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7e1cc-116">Compiling the code</span></span>

<span data-ttu-id="7e1cc-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7e1cc-117">This example requires:</span></span>

- <span data-ttu-id="7e1cc-118">, Что <xref:System> пространство имен должно быть импортировано с помощью оператора `using` C# (требуется в коде).</span><span class="sxs-lookup"><span data-stu-id="7e1cc-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e1cc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7e1cc-119">See also</span></span>

- [<span data-ttu-id="7e1cc-120">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="7e1cc-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="7e1cc-121">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="7e1cc-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="7e1cc-122">Практическое руководство. Создание экземпляра объекта TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="7e1cc-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
