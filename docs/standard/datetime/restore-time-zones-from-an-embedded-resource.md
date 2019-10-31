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
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Как восстановить Часовые пояса из внедренного ресурса

В этом разделе описывается восстановление часовых поясов, сохраненных в файле ресурсов. Сведения и инструкции по сохранению часовых поясов см. в статье [как сохранить Часовые пояса во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Десериализация объекта TimeZoneInfo из внедренного ресурса

1. Если часовой пояс для извлечения не является пользовательским часовым поясом, попробуйте создать его экземпляр с помощью метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.

2. Создайте экземпляр объекта <xref:System.Resources.ResourceManager>, передав полное имя внедренного файла ресурсов и ссылку на сборку, содержащую файл ресурсов.

   Если не удается определить полное имя внедренного файла ресурсов, используйте для проверки манифеста сборки [Ildasm. exe (ДИЗАССЕМБЛЕР IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) . Запись `.mresource` идентифицирует ресурс. В этом примере полное имя ресурса — `SerializeTimeZoneData.SerializedTimeZones`.

   Если файл ресурсов внедряется в ту же сборку, которая содержит код создания экземпляра часового пояса, можно получить ссылку на него, вызвав метод `static` (`Shared` в Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.

3. Если вызов метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> завершается ошибкой или создается пользовательский часовой пояс, извлеките строку, содержащую сериализованный часовой пояс, вызвав метод <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>.

4. Десериализация данных часового пояса путем вызова метода <xref:System.TimeZoneInfo.FromSerializedString%2A>.

## <a name="example"></a>Пример

В следующем примере десериализуется объект <xref:System.TimeZoneInfo>, хранящийся во внедренном файле ресурсов XML .NET.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Этот код иллюстрирует обработку исключений, чтобы убедиться в наличии объекта <xref:System.TimeZoneInfo>, требуемого для приложения. Сначала он пытается создать экземпляр объекта <xref:System.TimeZoneInfo>, извлекая его из реестра с помощью метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>. Если не удается создать экземпляр часового пояса, код извлекает его из файла внедренных ресурсов.

Поскольку данные для пользовательских часовых поясов (часовые пояса, созданные с помощью метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>) не хранятся в реестре, код не вызывает <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для создания экземпляра часового пояса для Палмер, Антарктида. Вместо этого он сразу же обращается к внедренному файлу ресурсов, чтобы получить строку, содержащую данные часового пояса, перед вызовом метода <xref:System.TimeZoneInfo.FromSerializedString%2A>.

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
