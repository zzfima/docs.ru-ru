---
title: "Как: сохранение часовых поясов во внедренном ресурсе"
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
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96dd3f0a3ed27a9e09c62f3ad4f450ced5a8e644
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="c181d-102">Как: сохранение часовых поясов во внедренном ресурсе</span><span class="sxs-lookup"><span data-stu-id="c181d-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="c181d-103">Часовому поясу приложение часто требуется наличие определенного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c181d-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="c181d-104">Тем не менее поскольку доступность отдельных <xref:System.TimeZoneInfo> объектов зависит от сведений, хранящихся в локальном реестре пользователя, даже настраиваемые доступные часовые пояса могут отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="c181d-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="c181d-105">Кроме того, сведения о настраиваемых часовых поясов, созданных с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода не сохраняется вместе с другими данными часового пояса в реестре.</span><span class="sxs-lookup"><span data-stu-id="c181d-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="c181d-106">Убедитесь, что доступны этих часовых поясах, при необходимости, можно сохранить их можно сериализовать и последующее восстановление их десериализовать.</span><span class="sxs-lookup"><span data-stu-id="c181d-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="c181d-107">Обычно сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения часовыми поясами.</span><span class="sxs-lookup"><span data-stu-id="c181d-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="c181d-108">В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, данные о часовом поясе может быть сериализован в рамках процедуры установки или настройки (например, если данные хранятся в ключе реестра), или как часть служебной процедуры, запускаемой Перед окончательной компиляцией приложения (например, когда сериализованные данные хранятся в файле ресурсов (RESX) .NET XML).</span><span class="sxs-lookup"><span data-stu-id="c181d-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="c181d-109">Помимо файла ресурсов, который компилируется с приложением можно использовать несколько хранилищ данных, информации о часовых поясах.</span><span class="sxs-lookup"><span data-stu-id="c181d-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="c181d-110">В число этих требований входят следующие:</span><span class="sxs-lookup"><span data-stu-id="c181d-110">These include the following:</span></span>

* <span data-ttu-id="c181d-111">Реестр.</span><span class="sxs-lookup"><span data-stu-id="c181d-111">The registry.</span></span> <span data-ttu-id="c181d-112">Обратите внимание, что приложение должно использовать подразделов раздела свои собственные приложения для хранения данных пользовательского часового пояса, а не с помощью подразделов параметру NT\CurrentVersion\Time зон.</span><span class="sxs-lookup"><span data-stu-id="c181d-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

* <span data-ttu-id="c181d-113">Файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c181d-113">Configuration files.</span></span>

* <span data-ttu-id="c181d-114">Другие системные файлы.</span><span class="sxs-lookup"><span data-stu-id="c181d-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="c181d-115">Для сохранения часового пояса путем сериализации его в RESX-файла</span><span class="sxs-lookup"><span data-stu-id="c181d-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="c181d-116">Извлечь существующий часовой пояс или создайте новый часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="c181d-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="c181d-117">Для получения существующий часовой пояс, [как: доступ к предопределенные объекты пояса UTC и местным временем](../../../docs/standard/datetime/access-utc-and-local.md) и [как: создание объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="c181d-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="c181d-118">Чтобы создать новый часовой пояс, вызовите одну из перегрузок <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="c181d-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="c181d-119">Дополнительные сведения см. в разделе [как: создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) и [как: создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="c181d-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="c181d-120">Вызовите <xref:System.TimeZoneInfo.ToSerializedString%2A> метод, чтобы создать строку, содержащую данные о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="c181d-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="c181d-121">Создать экземпляр <xref:System.IO.StreamWriter> , указав имя и при необходимости путь RESX-файл для <xref:System.IO.StreamWriter> конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="c181d-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="c181d-122">Создать экземпляр <xref:System.Resources.ResXResourceWriter> путем передачи <xref:System.IO.StreamWriter> объект <xref:System.Resources.ResXResourceWriter> конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="c181d-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="c181d-123">Передайте часового пояса в сериализованную строку для <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="c181d-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="c181d-124">Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c181d-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="c181d-125">Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c181d-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="c181d-126">Закрыть <xref:System.IO.StreamWriter> , вызывая его <xref:System.IO.StreamWriter.Close%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="c181d-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="c181d-127">Добавьте созданный RESX-файл в проект Visual Studio для приложения.</span><span class="sxs-lookup"><span data-stu-id="c181d-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="c181d-128">С помощью **свойства** в Visual Studio, убедитесь, что в RESX-файл **действие при построении** свойству **внедренный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="c181d-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="c181d-129">Пример</span><span class="sxs-lookup"><span data-stu-id="c181d-129">Example</span></span>

<span data-ttu-id="c181d-130">В следующем примере сериализуется <xref:System.TimeZoneInfo> , представляющий центральное стандартное время и <xref:System.TimeZoneInfo> объект, представляющий антарктическое время, сериализуются в файл ресурсов .NET XML, который называется SerializedTimeZones.resx.</span><span class="sxs-lookup"><span data-stu-id="c181d-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="c181d-131">Центральное стандартное время, обычно определяются в реестре; Антарктическое является пользовательский часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="c181d-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="c181d-132">В этом примере выполняется сериализация <xref:System.TimeZoneInfo> объектов, чтобы они были доступны в файле ресурсов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="c181d-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="c181d-133">Поскольку <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> метод добавляет полные сведения заголовка в файл ресурсов .NET XML, не может использоваться для добавления ресурсов в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="c181d-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="c181d-134">Этот пример проводит путем проверки файла SerializedTimeZones.resx и, если он существует, отличный от его ресурсы хранения этих двух сериализованных часовых поясов в универсальный тип <xref:System.Collections.Generic.Dictionary%602> объекта.</span><span class="sxs-lookup"><span data-stu-id="c181d-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="c181d-135">Существующий файл удаляется, а существующие ресурсы добавляются в новый файл SerializedTimeZones.resx.</span><span class="sxs-lookup"><span data-stu-id="c181d-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="c181d-136">Сериализованные данные часового пояса также добавляется в этот файл.</span><span class="sxs-lookup"><span data-stu-id="c181d-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="c181d-137">Ключ (или **имя**) полей ресурсов не должен содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="c181d-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="c181d-138"><xref:System.String.Replace%28System.String%2CSystem.String%29> Метод вызывается для удаления всех пробелов в идентификаторы часовых поясов, прежде чем они помещаются в файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c181d-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c181d-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c181d-139">Compiling the code</span></span>

<span data-ttu-id="c181d-140">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c181d-140">This example requires:</span></span>

* <span data-ttu-id="c181d-141">Чтобы ссылка System.Windows.Forms.dll и System.Core.dll была добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="c181d-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="c181d-142">Что импортируется следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="c181d-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="c181d-143">См. также</span><span class="sxs-lookup"><span data-stu-id="c181d-143">See also</span></span>

<span data-ttu-id="c181d-144">[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md)
[как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="c181d-144">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
