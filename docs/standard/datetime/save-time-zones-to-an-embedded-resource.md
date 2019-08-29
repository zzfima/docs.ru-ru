---
title: Практическое руководство. Сохранение часовых поясов во внедренном ресурсе
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca39d989cc7bc16ec2678ba5fa53710899f3ac4
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107156"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="81e06-102">Практическое руководство. Сохранение часовых поясов во внедренном ресурсе</span><span class="sxs-lookup"><span data-stu-id="81e06-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="81e06-103">Для приложения, поддерживающего Часовые пояса, часто требуется наличие определенного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="81e06-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="81e06-104">Однако, поскольку доступность отдельных <xref:System.TimeZoneInfo> объектов зависит от информации, хранящейся в реестре локальной системы, даже нестандартно доступные часовые пояса могут отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="81e06-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="81e06-105">Кроме того <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> , сведения о настраиваемых часовых поясах, создаваемых с помощью метода, не сохраняются с другими сведениями о часовом поясе в реестре.</span><span class="sxs-lookup"><span data-stu-id="81e06-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="81e06-106">Чтобы обеспечить доступность этих часовых поясов при необходимости, их можно сохранить путем их сериализации и последующего восстановления путем их десериализации.</span><span class="sxs-lookup"><span data-stu-id="81e06-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="81e06-107">Как правило, сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения, поддерживающего часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="81e06-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="81e06-108">В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, данные часового пояса могут быть сериализованы как часть программы установки или установки (например, когда данные хранятся в реестре) или в составе служебной программы, выполняемой перед компиляцией окончательного приложения (например, если сериализованные данные хранятся в файле ресурсов XML .NET (RESX)).</span><span class="sxs-lookup"><span data-stu-id="81e06-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="81e06-109">Помимо файла ресурсов, компилируемого с приложением, для сведений о часовом поясе можно использовать несколько других хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="81e06-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="81e06-110">следующие основные параметры.</span><span class="sxs-lookup"><span data-stu-id="81e06-110">These include the following:</span></span>

- <span data-ttu-id="81e06-111">Реестр.</span><span class="sxs-lookup"><span data-stu-id="81e06-111">The registry.</span></span> <span data-ttu-id="81e06-112">Обратите внимание, что приложение должно использовать подразделы собственного ключа приложения для хранения пользовательских данных часового пояса, а не использовать подразделы зон HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Nt\currentversion\time Zones.</span><span class="sxs-lookup"><span data-stu-id="81e06-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="81e06-113">Файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="81e06-113">Configuration files.</span></span>

- <span data-ttu-id="81e06-114">Другие системные файлы.</span><span class="sxs-lookup"><span data-stu-id="81e06-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="81e06-115">Сохранение часового пояса путем его сериализации в RESX-файл</span><span class="sxs-lookup"><span data-stu-id="81e06-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="81e06-116">Получение существующего часового пояса или создание нового часового пояса.</span><span class="sxs-lookup"><span data-stu-id="81e06-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="81e06-117">Чтобы получить существующий часовой пояс, см. [раздел как Доступ к стандартным объектам](../../../docs/standard/datetime/access-utc-and-local.md) времени в формате UTC и местному часовому поясу, а [также: Создайте экземпляр объекта](../../../docs/standard/datetime/instantiate-time-zone-info.md)TimeZoneInfo.</span><span class="sxs-lookup"><span data-stu-id="81e06-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="81e06-118">Чтобы создать новый часовой пояс, вызовите одну из перегрузок <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="81e06-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="81e06-119">Дополнительные сведения см. в разделе [Практическое руководство. Создавайте Часовые пояса без](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) правил [коррекции и выполняя следующие действия: Создание часовых поясов с правилами](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)коррекции.</span><span class="sxs-lookup"><span data-stu-id="81e06-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="81e06-120">Вызовите <xref:System.TimeZoneInfo.ToSerializedString%2A> метод, чтобы создать строку, содержащую данные часового пояса.</span><span class="sxs-lookup"><span data-stu-id="81e06-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="81e06-121">Создайте экземпляр <xref:System.IO.StreamWriter> объекта, указав имя и, при необходимости, путь к RESX-файлу конструктора класса. <xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="81e06-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="81e06-122">Создайте экземпляр <xref:System.IO.StreamWriter>объекта, передав объект в <xref:System.Resources.ResXResourceWriter> конструктор класса. <xref:System.Resources.ResXResourceWriter></span><span class="sxs-lookup"><span data-stu-id="81e06-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="81e06-123">Передайте сериализованную строку часового пояса в <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="81e06-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="81e06-124">Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81e06-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="81e06-125">Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81e06-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="81e06-126">Закройте объект, вызвав его <xref:System.IO.StreamWriter.Close%2A>метод. <xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="81e06-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="81e06-127">Добавьте созданный RESX файл в проект приложения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="81e06-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="81e06-128">С помощью окна **Свойства** в Visual Studio убедитесь, что для свойства **действие сборки** RESX-файла задано значение Внедренный **ресурс**.</span><span class="sxs-lookup"><span data-stu-id="81e06-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="81e06-129">Пример</span><span class="sxs-lookup"><span data-stu-id="81e06-129">Example</span></span>

<span data-ttu-id="81e06-130">В следующем примере сериализуется <xref:System.TimeZoneInfo> объект, представляющий центральное стандартное время, <xref:System.TimeZoneInfo> и объект, представляющий Палмер станцию, Антарктида время в файл ресурсов .NET XML с именем сериализедтимезонес. resx.</span><span class="sxs-lookup"><span data-stu-id="81e06-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="81e06-131">Центральное стандартное время обычно определяется в реестре; Палмер станция, Антарктида — настраиваемый часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="81e06-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="81e06-132">В этом примере сериализуются <xref:System.TimeZoneInfo> объекты, чтобы они были доступны в файле ресурсов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="81e06-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="81e06-133"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> Поскольку метод добавляет полные данные заголовка в файл ресурсов XML .NET, он не может использоваться для добавления ресурсов в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="81e06-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="81e06-134">Этот пример обрабатывает это путем проверки файла сериализедтимезонес. resx и (если он существует), сохраняя все ресурсы, кроме двух сериализованных часовых поясов, в универсальный <xref:System.Collections.Generic.Dictionary%602> объект.</span><span class="sxs-lookup"><span data-stu-id="81e06-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="81e06-135">После этого существующий файл удаляется, а существующие ресурсы добавляются в новый файл Сериализедтимезонес. resx.</span><span class="sxs-lookup"><span data-stu-id="81e06-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="81e06-136">Сериализованные данные часового пояса также добавляются в этот файл.</span><span class="sxs-lookup"><span data-stu-id="81e06-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="81e06-137">Поля ключа (или **имени**) ресурсов не должны содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="81e06-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="81e06-138"><xref:System.String.Replace%28System.String%2CSystem.String%29> Метод вызывается для удаления всех внедренных пробелов в идентификаторах часовых поясов до их назначения в файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="81e06-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="81e06-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="81e06-139">Compiling the code</span></span>

<span data-ttu-id="81e06-140">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="81e06-140">This example requires:</span></span>

- <span data-ttu-id="81e06-141">Ссылка на библиотеку System. Windows. Forms. dll и System. Core. dll будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="81e06-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="81e06-142">Для импорта следующих пространств имен:</span><span class="sxs-lookup"><span data-stu-id="81e06-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="81e06-143">См. также</span><span class="sxs-lookup"><span data-stu-id="81e06-143">See also</span></span>

- [<span data-ttu-id="81e06-144">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="81e06-144">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="81e06-145">Общие сведения о часовых поясах</span><span class="sxs-lookup"><span data-stu-id="81e06-145">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="81e06-146">Практическое руководство. Восстановление часовых поясов из внедренного ресурса</span><span class="sxs-lookup"><span data-stu-id="81e06-146">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
