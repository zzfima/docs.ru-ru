---
title: Как восстановить Часовые пояса из внедренного ресурса
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122191"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="92dcf-102">Как восстановить Часовые пояса из внедренного ресурса</span><span class="sxs-lookup"><span data-stu-id="92dcf-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="92dcf-103">В этом разделе описывается восстановление часовых поясов, сохраненных в файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="92dcf-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="92dcf-104">Сведения и инструкции по сохранению часовых поясов см. в статье [как сохранить Часовые пояса во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="92dcf-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="92dcf-105">Десериализация объекта TimeZoneInfo из внедренного ресурса</span><span class="sxs-lookup"><span data-stu-id="92dcf-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="92dcf-106">Если часовой пояс для извлечения не является пользовательским часовым поясом, попробуйте создать его экземпляр с помощью метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.</span><span class="sxs-lookup"><span data-stu-id="92dcf-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="92dcf-107">Создайте экземпляр объекта <xref:System.Resources.ResourceManager>, передав полное имя внедренного файла ресурсов и ссылку на сборку, содержащую файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="92dcf-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="92dcf-108">Если не удается определить полное имя внедренного файла ресурсов, используйте для проверки манифеста сборки [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) .</span><span class="sxs-lookup"><span data-stu-id="92dcf-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="92dcf-109">Запись `.mresource` идентифицирует ресурс.</span><span class="sxs-lookup"><span data-stu-id="92dcf-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="92dcf-110">В этом примере полное имя ресурса — `SerializeTimeZoneData.SerializedTimeZones`.</span><span class="sxs-lookup"><span data-stu-id="92dcf-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="92dcf-111">Если файл ресурсов внедряется в ту же сборку, которая содержит код создания экземпляра часового пояса, можно получить ссылку на него, вызвав метод `static` (`Shared` в Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="92dcf-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="92dcf-112">Если вызов метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> завершается ошибкой или создается пользовательский часовой пояс, извлеките строку, содержащую сериализованный часовой пояс, вызвав метод <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="92dcf-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="92dcf-113">Десериализация данных часового пояса путем вызова метода <xref:System.TimeZoneInfo.FromSerializedString%2A>.</span><span class="sxs-lookup"><span data-stu-id="92dcf-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="92dcf-114">Пример</span><span class="sxs-lookup"><span data-stu-id="92dcf-114">Example</span></span>

<span data-ttu-id="92dcf-115">В следующем примере десериализуется объект <xref:System.TimeZoneInfo>, хранящийся во внедренном файле ресурсов XML .NET.</span><span class="sxs-lookup"><span data-stu-id="92dcf-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="92dcf-116">Этот код иллюстрирует обработку исключений, чтобы убедиться в наличии объекта <xref:System.TimeZoneInfo>, требуемого для приложения.</span><span class="sxs-lookup"><span data-stu-id="92dcf-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="92dcf-117">Сначала он пытается создать экземпляр объекта <xref:System.TimeZoneInfo>, извлекая его из реестра с помощью метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.</span><span class="sxs-lookup"><span data-stu-id="92dcf-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="92dcf-118">Если не удается создать экземпляр часового пояса, код извлекает его из файла внедренных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="92dcf-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="92dcf-119">Поскольку данные для пользовательских часовых поясов (часовые пояса, созданные с помощью метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>) не хранятся в реестре, код не вызывает <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для создания экземпляра часового пояса для Палмер, Антарктида.</span><span class="sxs-lookup"><span data-stu-id="92dcf-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="92dcf-120">Вместо этого он сразу же обращается к внедренному файлу ресурсов, чтобы получить строку, содержащую данные часового пояса, перед вызовом метода <xref:System.TimeZoneInfo.FromSerializedString%2A>.</span><span class="sxs-lookup"><span data-stu-id="92dcf-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="92dcf-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="92dcf-121">Compiling the code</span></span>

<span data-ttu-id="92dcf-122">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="92dcf-122">This example requires:</span></span>

- <span data-ttu-id="92dcf-123">Ссылка на библиотеку System. Windows. Forms. dll и System. Core. dll будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="92dcf-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="92dcf-124">Для импорта следующих пространств имен:</span><span class="sxs-lookup"><span data-stu-id="92dcf-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="92dcf-125">См. также</span><span class="sxs-lookup"><span data-stu-id="92dcf-125">See also</span></span>

- [<span data-ttu-id="92dcf-126">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="92dcf-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="92dcf-127">Общие сведения о часовых поясах</span><span class="sxs-lookup"><span data-stu-id="92dcf-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="92dcf-128">Практическое руководство. Сохранение часовых поясов во внедренном ресурсе</span><span class="sxs-lookup"><span data-stu-id="92dcf-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
