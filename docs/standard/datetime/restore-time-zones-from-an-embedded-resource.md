---
title: Практическое руководство. Восстановление часовых поясов из внедренного ресурса
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
ms.openlocfilehash: 98813bf6685be78d33ebd5cc5e8c07a61a811c25
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106752"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Практическое руководство. Восстановление часовых поясов из внедренного ресурса

В этом разделе описывается восстановление часовых поясов, сохраненных в файле ресурсов. Сведения и инструкции по сохранению часовых поясов см [. в разделе как Сохраняйте Часовые пояса во внедренном](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)ресурсе.

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Десериализация объекта TimeZoneInfo из внедренного ресурса

1. Если часовой пояс для извлечения не является пользовательским часовым поясом, попробуйте создать его экземпляр с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метода.

2. Создайте экземпляр объекта, передав полное имя внедренного файла ресурсов и ссылку на сборку, содержащую файл ресурсов. <xref:System.Resources.ResourceManager>

   Если не удается определить полное имя внедренного файла ресурсов, используйте для проверки манифеста сборки [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) . `.mresource` Запись идентифицирует ресурс. В этом примере полное имя ресурса — `SerializeTimeZoneData.SerializedTimeZones`.

   Если файл ресурсов внедрен в ту же сборку, которая содержит код создания экземпляра часового пояса, можно получить ссылку на него, вызвав `static` метод (`Shared` в Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .

3. Если вызов <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метода завершается с ошибкой или если требуется создать пользовательский часовой пояс, извлеките строку, содержащую сериализованный часовой пояс, <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> вызвав метод.

4. Десериализация данных часового пояса путем вызова <xref:System.TimeZoneInfo.FromSerializedString%2A> метода.

## <a name="example"></a>Пример

В следующем примере десериализуется объект <xref:System.TimeZoneInfo> , хранящийся во внедренном XML-файле ресурсов .NET.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Этот код иллюстрирует обработку исключений, <xref:System.TimeZoneInfo> чтобы убедиться в наличии объекта, требуемого для приложения. Сначала он пытается создать экземпляр <xref:System.TimeZoneInfo> объекта, извлекая его из реестра <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> с помощью метода. Если не удается создать экземпляр часового пояса, код извлекает его из файла внедренных ресурсов.

Поскольку данные для пользовательских часовых поясов (часовые пояса, созданные с <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> помощью метода) не хранятся в реестре, код не <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> вызывает метод для создания экземпляра часового пояса для Палмер, Антарктида. Вместо этого он сразу же обращается к внедренному файлу ресурсов для получения строки, содержащей данные часового пояса перед вызовом <xref:System.TimeZoneInfo.FromSerializedString%2A> метода.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Ссылка на библиотеку System. Windows. Forms. dll и System. Core. dll будет добавлена в проект.

- Для импорта следующих пространств имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)
- [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
