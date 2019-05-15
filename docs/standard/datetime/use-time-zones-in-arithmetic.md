---
title: Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d504aa9ad7d6e4084192a2434ac408e8fa7a041
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588541"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="509c4-102">Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем</span><span class="sxs-lookup"><span data-stu-id="509c4-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="509c4-103">Как правило, при выполнения дату и время арифметических <xref:System.DateTime> или <xref:System.DateTimeOffset> значения, результат не отражают правила коррекции часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="509c4-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="509c4-104">Это верно, даже если часовой пояс значения даты и времени четко определен (например, в том случае, когда <xref:System.DateTime.Kind%2A> свойству <xref:System.DateTimeKind.Local>).</span><span class="sxs-lookup"><span data-stu-id="509c4-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="509c4-105">В этом разделе показано, как выполнять арифметические операции над значениями даты и времени, которые принадлежат к определенному часовому поясу.</span><span class="sxs-lookup"><span data-stu-id="509c4-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="509c4-106">Результаты арифметических операций при этом будут учитывать правила коррекции часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="509c4-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="509c4-107">Применение правил коррекции в вычислениях с датами и временем</span><span class="sxs-lookup"><span data-stu-id="509c4-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="509c4-108">Необходимо каким-либо способом тесно связать значения даты и времени с соответствующим часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="509c4-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="509c4-109">К примеру, можно объявить структуру, которая будет содержать значение даты и времени вместе с данными о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="509c4-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="509c4-110">В следующем примере используется этот подход, чтобы связать <xref:System.DateTime> значение с его часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="509c4-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="509c4-111">Преобразования времени в формате UTC в формате UTC с помощью вызова <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> метод или <xref:System.TimeZoneInfo.ConvertTime%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="509c4-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="509c4-112">Далее следует выполнить необходимые арифметические действия над временем UTC.</span><span class="sxs-lookup"><span data-stu-id="509c4-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="509c4-113">Преобразовать время от времени UTC в исходное время связаны с часовым поясом, вызвав <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="509c4-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="509c4-114">Пример</span><span class="sxs-lookup"><span data-stu-id="509c4-114">Example</span></span>

<span data-ttu-id="509c4-115">В следующем примере к 9 марта 2008 г., 1:30</span><span class="sxs-lookup"><span data-stu-id="509c4-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="509c4-116">центрального стандартного времени прибавляется два часа и тридцать минут.</span><span class="sxs-lookup"><span data-stu-id="509c4-116">Central Standard Time.</span></span> <span data-ttu-id="509c4-117">Переход на летнее время в этом часовом поясе происходит на 30 минут позже, в 2:00</span><span class="sxs-lookup"><span data-stu-id="509c4-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="509c4-118">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="509c4-118">on March 9, 2008.</span></span> <span data-ttu-id="509c4-119">Поскольку в этом примере выполнены четыре шага, описанные в предыдущем разделе, он правильно возвращает итоговое время, равное 5:00</span><span class="sxs-lookup"><span data-stu-id="509c4-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="509c4-120">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="509c4-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="509c4-121">Оба <xref:System.DateTime> и <xref:System.DateTimeOffset> значения являются отделяется от любой часовой пояс, к которому они могут относиться.</span><span class="sxs-lookup"><span data-stu-id="509c4-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="509c4-122">Для того чтобы арифметические действия с датами и временем выполнялись таким образом, что правила коррекции часовых поясов учитывались бы автоматически, сведения о часовом поясе, к которому относятся значения даты и времени, должны быть известны и непосредственно доступны.</span><span class="sxs-lookup"><span data-stu-id="509c4-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="509c4-123">Это означает, что значения даты и времени должны быть тесно связаны с часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="509c4-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="509c4-124">Для того, чтобы этого добиться, существует целый ряд способов, некоторые из них перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="509c4-124">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="509c4-125">Предположим, что все значения времени, используемые в приложении, принадлежат к определенному часовому поясу.</span><span class="sxs-lookup"><span data-stu-id="509c4-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="509c4-126">Хотя этот подход вполне применим во многих случаях, его гибкость и, возможно, переносимость имеют ограничения.</span><span class="sxs-lookup"><span data-stu-id="509c4-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="509c4-127">Следует определить тип, в котором значение даты и времени тесно связано с часовым поясом, включив эти данные в состав типа в качестве полей.</span><span class="sxs-lookup"><span data-stu-id="509c4-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="509c4-128">Этот подход используется в примере кода — в нем определяется структура для хранения даты, времени и часового пояса в двух полях структуры.</span><span class="sxs-lookup"><span data-stu-id="509c4-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="509c4-129">В примере способов выполнения арифметических операций с <xref:System.DateTime> значений, чтобы результат применения правила коррекции часового пояса.</span><span class="sxs-lookup"><span data-stu-id="509c4-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="509c4-130">Тем не менее <xref:System.DateTimeOffset> значения могут использоваться в легко.</span><span class="sxs-lookup"><span data-stu-id="509c4-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="509c4-131">В следующем примере показано, как в примере исходного кода могут быть адаптированы к использованию <xref:System.DateTimeOffset> вместо <xref:System.DateTime> значения.</span><span class="sxs-lookup"><span data-stu-id="509c4-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="509c4-132">Обратите внимание, что если эта операция выполняется над <xref:System.DateTimeOffset> значение без сначала преобразуется в формат UTC, результат будет соответствовать правильному моменту времени, но его смещение не соответствующим образом изменит заданный часовой пояс для времени.</span><span class="sxs-lookup"><span data-stu-id="509c4-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="509c4-133">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="509c4-133">Compiling the code</span></span>

<span data-ttu-id="509c4-134">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="509c4-134">This example requires:</span></span>

* <span data-ttu-id="509c4-135">Что <xref:System> импорт пространства имен с помощью `using` инструкции (обязательно в коде C#).</span><span class="sxs-lookup"><span data-stu-id="509c4-135">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="509c4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="509c4-136">See also</span></span>

- [<span data-ttu-id="509c4-137">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="509c4-137">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="509c4-138">Выполнение арифметических операций с датами и временем</span><span class="sxs-lookup"><span data-stu-id="509c4-138">Performing arithmetic operations with dates and times</span></span>](../../../docs/standard/datetime/performing-arithmetic-operations.md)
