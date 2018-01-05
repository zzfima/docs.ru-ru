---
title: "Как: создание объекта TimeZoneInfo"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59c23b4517e1150a8b17dd41667f3e793809fd21
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="37cf3-102">Как: создание объекта TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="37cf3-102">How to: Instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="37cf3-103">Наиболее распространенный способ создания экземпляра объекта <xref:System.TimeZoneInfo> — получение сведений о нем из реестра.</span><span class="sxs-lookup"><span data-stu-id="37cf3-103">The most common way to instantiate a <xref:System.TimeZoneInfo> object is to retrieve information about it from the registry.</span></span> <span data-ttu-id="37cf3-104">В этом разделе описываются способы создания экземпляра объекта <xref:System.TimeZoneInfo> на основе локального системного реестра.</span><span class="sxs-lookup"><span data-stu-id="37cf3-104">This topic discusses how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

### <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="37cf3-105">Создание экземпляра объекта TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="37cf3-105">To instantiate a TimeZoneInfo object</span></span>

1. <span data-ttu-id="37cf3-106">Объявите объект <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="37cf3-106">Declare a <xref:System.TimeZoneInfo> object.</span></span>

2. <span data-ttu-id="37cf3-107">Вызовите `static` (`Shared` в Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="37cf3-107">Call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method.</span></span>

3. <span data-ttu-id="37cf3-108">Обработайте исключения, созданные этим методом, особенно <xref:System.TimeZoneNotFoundException> , создаваемое, если в реестре не определен часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="37cf3-108">Handle any exceptions thrown by the method, particularly the <xref:System.TimeZoneNotFoundException> that is thrown if the time zone is not defined in the registry.</span></span>

## <a name="example"></a><span data-ttu-id="37cf3-109">Пример</span><span class="sxs-lookup"><span data-stu-id="37cf3-109">Example</span></span>

<span data-ttu-id="37cf3-110">Следующий код извлекает объект <xref:System.TimeZoneInfo> , который представляет часовой пояс восточного времени США, и отображает время в этом поясе, соответствующее местному времени.</span><span class="sxs-lookup"><span data-stu-id="37cf3-110">The following code retrieves a <xref:System.TimeZoneInfo> object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<span data-ttu-id="37cf3-111"><xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> Единственный параметр метода является идентификатор часового пояса, которую требуется получить, соответствующий объекту <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="37cf3-111">The <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="37cf3-112">Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="37cf3-112">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="37cf3-113">Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный.</span><span class="sxs-lookup"><span data-stu-id="37cf3-113">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="37cf3-114">В большинстве случаев его значение соответствует свойству <xref:System.TimeZoneInfo.StandardName%2A> объекта <xref:System.TimeZoneInfo> , которое используется для предоставления имени стандартного времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="37cf3-114">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A> property of a <xref:System.TimeZoneInfo> object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="37cf3-115">Однако существуют исключения.</span><span class="sxs-lookup"><span data-stu-id="37cf3-115">However, there are exceptions.</span></span> <span data-ttu-id="37cf3-116">Лучше всего гарантировать, что передается действительный идентификатор, путем перечисления доступных в системе часовых поясов и отслеживания присутствующих в них идентификаторов часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="37cf3-116">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="37cf3-117">Пример см. в разделе [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="37cf3-117">For an illustration, see [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span></span> <span data-ttu-id="37cf3-118">Раздел [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) также содержит список идентификаторов избранных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="37cf3-118">The [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="37cf3-119">Если часовой пояс найден, метод возвращает его объект <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="37cf3-119">If the time zone is found, the method returns its <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="37cf3-120">Если часовой пояс не найден, метод создает <xref:System.TimeZoneNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="37cf3-120">If the time zone is not found, the method throws a <xref:System.TimeZoneNotFoundException>.</span></span> <span data-ttu-id="37cf3-121">Если часовой пояс найден, но его данные повреждены или неполны, метод создает <xref:System.InvalidTimeZoneException>.</span><span class="sxs-lookup"><span data-stu-id="37cf3-121">If the time zone is found but its data is corrupted or incomplete, the method throws an <xref:System.InvalidTimeZoneException>.</span></span>

<span data-ttu-id="37cf3-122">Если приложение зависит от наличия часового пояса, необходимо сначала вызвать метод <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для извлечения сведений о часовом поясе из реестра.</span><span class="sxs-lookup"><span data-stu-id="37cf3-122">If your application relies on a time zone that must be present, you should first call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method to retrieve the time zone information from the registry.</span></span> <span data-ttu-id="37cf3-123">Если вызов метода завершится сбоем, обработчик исключений должен создать новый экземпляр часового пояса или повторно создать его путем десериализации сериализованного объекта <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="37cf3-123">If the method call fails, your exception handler should then either create a new instance of the time zone or re-create it by deserializing a serialized <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="37cf3-124">В разделе [как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="37cf3-124">See [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) for an example.</span></span>

## <a name="see-also"></a><span data-ttu-id="37cf3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="37cf3-125">See also</span></span>

<span data-ttu-id="37cf3-126">[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[поиск часового пояса, определенные в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[как: доступ к объектам стандартных UTC и местным временем зоны](../../../docs/standard/datetime/access-utc-and-local.md)</span><span class="sxs-lookup"><span data-stu-id="37cf3-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)</span></span>
