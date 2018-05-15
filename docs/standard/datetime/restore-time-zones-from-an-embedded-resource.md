---
title: 'Как: восстановление часовых поясов из внедренного ресурса'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31dd785c419d9a8e11eb23deabd2dfa71c4d6e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="b1f10-102">Как: восстановление часовых поясов из внедренного ресурса</span><span class="sxs-lookup"><span data-stu-id="b1f10-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="b1f10-103">В этом разделе описывается восстановление часовых поясов, которые были сохранены в файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b1f10-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="b1f10-104">Сведения и инструкции по сохранению часовых поясов см. в разделе [как: сохранение часовых поясов во внедренный ресурс](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="b1f10-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="b1f10-105">Для десериализации объекта TimeZoneInfo из внедренного ресурса</span><span class="sxs-lookup"><span data-stu-id="b1f10-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="b1f10-106">Если часовой пояс должны быть получены не пользовательский часовой пояс, попытайтесь создать его экземпляр с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b1f10-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="b1f10-107">Создать экземпляр <xref:System.Resources.ResourceManager> путем передачи полное имя файла внедренных ресурсов и ссылку на сборку, которая содержит файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b1f10-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="b1f10-108">Если не удается определить полное имя файла внедренных ресурсов, используйте [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для проверки манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="b1f10-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="b1f10-109">`.mresource` Идентифицирует ресурс.</span><span class="sxs-lookup"><span data-stu-id="b1f10-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="b1f10-110">В примере, является полное имя ресурса `SerializeTimeZoneData.SerializedTimeZones`.</span><span class="sxs-lookup"><span data-stu-id="b1f10-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="b1f10-111">Если файл ресурсов внедрен в той же сборке, который содержит код экземпляра часового пояса, ссылку на него можно получить, вызвав `static` (`Shared` в Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b1f10-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="b1f10-112">Если вызов <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метод завершается ошибкой, или если пользовательский часовой пояс, для создания экземпляра получения строка, содержащая сериализованный часовой пояс, вызвав <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="b1f10-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="b1f10-113">Десериализации данных часового пояса путем вызова <xref:System.TimeZoneInfo.FromSerializedString%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b1f10-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="b1f10-114">Пример</span><span class="sxs-lookup"><span data-stu-id="b1f10-114">Example</span></span>

<span data-ttu-id="b1f10-115">В следующем примере десериализуется <xref:System.TimeZoneInfo> объекта, хранящегося в внедренного файла ресурсов .NET XML.</span><span class="sxs-lookup"><span data-stu-id="b1f10-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="b1f10-116">Этот код иллюстрирует обработку исключений, чтобы убедиться, что <xref:System.TimeZoneInfo> присутствует объект, который требуется приложению.</span><span class="sxs-lookup"><span data-stu-id="b1f10-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="b1f10-117">Сначала пытается создать экземпляр <xref:System.TimeZoneInfo> объекта путем получения его из реестра с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b1f10-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="b1f10-118">Не удается создать экземпляр часового пояса, код получает из файла внедренных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b1f10-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="b1f10-119">Так как данные для пользовательских часовых поясов (часовых поясов, созданных с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод) не хранятся в реестре, код не вызывает <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для создания часового пояса Антарктики.</span><span class="sxs-lookup"><span data-stu-id="b1f10-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="b1f10-120">Вместо этого код сразу обращается к файлу внедренных ресурсов, необходимо получить строку, содержащую данные о часовом поясе, перед вызовом <xref:System.TimeZoneInfo.FromSerializedString%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b1f10-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="b1f10-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b1f10-121">Compiling the code</span></span>

<span data-ttu-id="b1f10-122">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b1f10-122">This example requires:</span></span>

* <span data-ttu-id="b1f10-123">Чтобы ссылка System.Windows.Forms.dll и System.Core.dll была добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="b1f10-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="b1f10-124">Что импортируется следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="b1f10-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="b1f10-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b1f10-125">See also</span></span>

<span data-ttu-id="b1f10-126">[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md)
[как: сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="b1f10-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)</span></span>
