---
title: "Как: перечисление часовых поясов, присутствующих на компьютере"
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
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f77afc8a0f2e6c110f4dc037c12ecc8b06908e60
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="45bca-102">Как: перечисление часовых поясов, присутствующих на компьютере</span><span class="sxs-lookup"><span data-stu-id="45bca-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="45bca-103">Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе.</span><span class="sxs-lookup"><span data-stu-id="45bca-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="45bca-104">В операционных системах Windows XP и Windows Vista сохранить эту информацию в реестре.</span><span class="sxs-lookup"><span data-stu-id="45bca-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="45bca-105">Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них.</span><span class="sxs-lookup"><span data-stu-id="45bca-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="45bca-106">Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям.</span><span class="sxs-lookup"><span data-stu-id="45bca-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="45bca-107">В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе.</span><span class="sxs-lookup"><span data-stu-id="45bca-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="45bca-108">Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора.</span><span class="sxs-lookup"><span data-stu-id="45bca-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="45bca-109">Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="45bca-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="45bca-110">Если приложение зависит от наличия определенного часового пояса, не могут быть определены в локальной системе, приложение может проверить его наличие, сериализацию и десериализацию сведений о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="45bca-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="45bca-111">Часовой пояс можно добавить элемент управления списка, затем, чтобы пользователь приложения можно выбрать его.</span><span class="sxs-lookup"><span data-stu-id="45bca-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="45bca-112">Дополнительные сведения см. в разделе [как: сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) и [как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="45bca-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="45bca-113">Перечисление часовых поясов, присутствующих в локальной системе</span><span class="sxs-lookup"><span data-stu-id="45bca-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="45bca-114">Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45bca-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="45bca-115">Метод возвращает универсальный <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="45bca-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="45bca-116">Элементы коллекции сортируются по их <xref:System.TimeZoneInfo.DisplayName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="45bca-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="45bca-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="45bca-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="45bca-118">Перечислите отдельные <xref:System.TimeZoneInfo> объектов в коллекции с помощью `foreach` (в C#) или `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="45bca-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="45bca-119">цикл (в Visual Basic) и выполните все необходимые действия для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="45bca-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="45bca-120">Например, следующий код перечисляет <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов возвращенную на шаге 1 и перечислены отображаемое имя каждого часового пояса на консоль.</span><span class="sxs-lookup"><span data-stu-id="45bca-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="45bca-121">Чтобы предоставить пользователю список часовых поясов, присутствующих в локальной системе</span><span class="sxs-lookup"><span data-stu-id="45bca-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="45bca-122">Вызовите метод <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45bca-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="45bca-123">Метод возвращает универсальный <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> коллекцию <xref:System.TimeZoneInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="45bca-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="45bca-124">Назначить коллекцию, возвращенную на шаге 1, `DataSource` свойство Windows forms или ASP.NET списка элемента управления.</span><span class="sxs-lookup"><span data-stu-id="45bca-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="45bca-125">Получить <xref:System.TimeZoneInfo> объект, выбранный пользователем.</span><span class="sxs-lookup"><span data-stu-id="45bca-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="45bca-126">Приведен пример для приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="45bca-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="45bca-127">Пример</span><span class="sxs-lookup"><span data-stu-id="45bca-127">Example</span></span>

<span data-ttu-id="45bca-128">В примере запускается приложение Windows, отображает часовые пояса, определенные в системе, в поле со списком.</span><span class="sxs-lookup"><span data-stu-id="45bca-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="45bca-129">Затем отображается диалоговое окно, содержащее значение <xref:System.TimeZoneInfo.DisplayName%2A> свойства объекта часового пояса, выбранного пользователем.</span><span class="sxs-lookup"><span data-stu-id="45bca-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="45bca-130">Наиболее список элементов управления (таких как <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> или <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> управления) для присвоения коллекцию объектные переменные, их `DataSource` при условии, что коллекция реализует свойство <xref:System.Collections.IEnumerable> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="45bca-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="45bca-131">(Универсальный <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> класса делает это.) Чтобы отобразить отдельный объект в коллекции, элемент управления вызывает этот объект `ToString` метод для извлечения строки, которая используется для представления объекта.</span><span class="sxs-lookup"><span data-stu-id="45bca-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="45bca-132">В случае использования <xref:System.TimeZoneInfo> объектов, `ToString` возвращает <xref:System.TimeZoneInfo> отображаемое имя объекта (значение его <xref:System.TimeZoneInfo.DisplayName%2A> свойство).</span><span class="sxs-lookup"><span data-stu-id="45bca-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="45bca-133">Так как элементы управления списком вызов объекта `ToString` метод, можно назначить коллекцию <xref:System.TimeZoneInfo> объектов с элементом управления, установить элемент управления отображать понятное имя для каждого объекта и получить <xref:System.TimeZoneInfo> объект, выбранный пользователем.</span><span class="sxs-lookup"><span data-stu-id="45bca-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="45bca-134">Это избавляет от необходимости извлекать строку для каждого объекта в коллекции, назначьте строку коллекции, в свою очередь назначенный к элементу управления `DataSource` свойство, получения строки, выбранном пользователем, а затем использовать эту строку для извлечения объекта Описывает, что он.</span><span class="sxs-lookup"><span data-stu-id="45bca-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="45bca-135">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="45bca-135">Compiling the code</span></span>

<span data-ttu-id="45bca-136">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="45bca-136">This example requires:</span></span>

* <span data-ttu-id="45bca-137">Чтобы ссылка на System.Core.dll была добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="45bca-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="45bca-138">Что импортируется следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="45bca-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="45bca-139"><xref:System>(в коде C#)</span><span class="sxs-lookup"><span data-stu-id="45bca-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="45bca-140">См. также</span><span class="sxs-lookup"><span data-stu-id="45bca-140">See also</span></span>

<span data-ttu-id="45bca-141">[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[как: сохранение часовых поясов во внедренный ресурс](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="45bca-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
