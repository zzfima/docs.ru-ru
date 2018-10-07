---
title: 'Практическое: восстановление часовых поясов из внедренного ресурса'
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
ms.openlocfilehash: 99d38b336b5e655dd1c96682eec90c5fbe8469d6
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841063"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Практическое: восстановление часовых поясов из внедренного ресурса

В этом разделе описывается восстановление часовых поясов, которые были сохранены в файле ресурсов. Сведения и инструкции по сохранению часовых поясов см. в разделе [как: сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Для десериализации объекта TimeZoneInfo из внедренного ресурса

1. Если часовой пояс извлекаемых не пользовательский часовой пояс, попытайтесь создать его экземпляр с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метод.

2. Создать экземпляр <xref:System.Resources.ResourceManager> объекта, передав полное имя файла внедренного ресурса и ссылку на сборку, которая содержит файл ресурсов.

   Если не удается определить полное имя файла внедренного ресурса, используйте [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для проверки манифеста сборки. `.mresource` Идентифицирует ресурс. В примере, является полное имя ресурса `SerializeTimeZoneData.SerializedTimeZones`.

   Если файл ресурсов внедряется в той же сборке, который содержит код создания экземпляра часового пояса, ссылку на него можно получить, вызвав `static` (`Shared` в Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> метод.

3. Если вызов <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метод завершается ошибкой, или если экземпляр которой необходимо создать пользовательский часовой пояс, получить строка, содержащая сериализованный часовой пояс, вызвав <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> метод.

4. Десериализации данных часового пояса путем вызова <xref:System.TimeZoneInfo.FromSerializedString%2A> метод.

## <a name="example"></a>Пример

В следующем примере десериализуется <xref:System.TimeZoneInfo> объект, хранящийся во внедренном файле ресурсов .NET XML.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Этот код иллюстрирует обработку исключений, чтобы убедиться, что <xref:System.TimeZoneInfo> присутствует объект, необходимый для приложения. Сначала выполняется попытка создать экземпляр <xref:System.TimeZoneInfo> путем извлечения его из реестра с помощью <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> метод. Если часовой пояс не может быть создан, код получает его из файла внедренных ресурсов.

Так как данные для пользовательских часовых поясов (часовых поясов, созданных с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод) не хранятся в реестре, код не вызывает <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для создания экземпляра часового пояса Антарктики. Вместо этого он немедленно проверяет файл внедренных ресурсов для получения строки, которая содержит данные о часовом поясе, перед вызовом <xref:System.TimeZoneInfo.FromSerializedString%2A> метод.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы добавить в проект ссылку на System.Windows.Forms.dll и System.Core.dll.

* Что импортируется следующие пространства имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также

* [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
* [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)
* [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
