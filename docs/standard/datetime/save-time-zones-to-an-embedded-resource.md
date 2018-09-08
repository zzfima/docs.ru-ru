---
title: 'Практическое: сохранение часовых поясов во внедренном ресурсе'
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
ms.openlocfilehash: 921874e774d18751c29db495dac1bc53d10cc8ad
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211857"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Практическое: сохранение часовых поясов во внедренном ресурсе

Часовыми поясами приложения часто требует наличия определенного часового пояса. Тем не менее поскольку доступность отдельных <xref:System.TimeZoneInfo> объектов зависит от сведений, хранящихся в реестре локальной системы, даже настраиваемые доступные часовые пояса могут отсутствовать. Кроме того, сведения о пользовательских часовых поясов, созданных с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода не сохраняется вместе с другими данными часового пояса в реестре. Чтобы убедиться, что эти часовые пояса доступны, когда они нужны, можно сохранить их можно сериализовать и последующее восстановление их десериализовать.

Обычно сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения, поддерживающих часовые пояса. В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, можно было сериализовать данные о часовом поясе, в рамках установки (например, когда данные хранятся в ключе реестра), или как часть программы подпрограмму, которая выполняется Прежде чем итоговое приложение компилируется, (например, когда сериализованные данные хранятся в файле ресурсов (.resx) .NET XML).

В дополнение к файлу ресурсов, который компилируется с приложением можно использовать несколько хранилищ данных для сведений о часовом поясе. В число этих требований входят следующие:

* Реестр. Обратите внимание на то, что в приложении необходимо использовать для хранения данных пользовательского часового пояса, а не с помощью подразделов HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones подразделов раздела свои собственные приложения.

* Файлы конфигурации.

* Другие системные файлы.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Для сохранения часового пояса путем сериализации его RESX-файла

1. Получить существующий часовой пояс или создайте новый часовой пояс.

   Чтобы извлечь существующий часовой пояс, см. в разделе [как: доступ к предварительно определенным объектам UTC и местным временем объектам зоны](../../../docs/standard/datetime/access-utc-and-local.md) и [как: создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Чтобы создать новый часовой пояс, вызовите одну из перегрузок <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод. Дополнительные сведения см. в разделе [как: создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) и [как: создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Вызовите <xref:System.TimeZoneInfo.ToSerializedString%2A> метод, чтобы создать строку, которая содержит данные часового пояса.

3. Создать экземпляр <xref:System.IO.StreamWriter> , указав имя и при необходимости путь файла .resx для <xref:System.IO.StreamWriter> конструктора класса.

4. Создать экземпляр <xref:System.Resources.ResXResourceWriter> путем передачи <xref:System.IO.StreamWriter> объект <xref:System.Resources.ResXResourceWriter> конструктора класса.

5. PASS часовой пояс в сериализованную строку для <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> метод.

6. Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Закрыть <xref:System.IO.StreamWriter> , вызвав его <xref:System.IO.StreamWriter.Close%2A> метод.

9. Добавьте созданный RESX-файл в проект приложения Visual Studio.

10. С помощью **свойства** окно в Visual Studio, убедитесь, что RESX-файл **действие при построении** свойству **внедренный ресурс**.

## <a name="example"></a>Пример

В следующем примере сериализуется <xref:System.TimeZoneInfo> , представляющий центральное стандартное время и <xref:System.TimeZoneInfo> объект, представляющий файл ресурсов .NET XML с именем SerializedTimeZones.resx станция Палмер время, сериализуются. Центральное стандартное время обычно определяется в реестре; Станция Палмер является пользовательский часовой пояс.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

Этот пример сериализует <xref:System.TimeZoneInfo> объектов, чтобы они были доступны в файле ресурсов во время компиляции.

Так как <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> метод добавляет полные сведения заголовка в файл ресурсов .NET XML, он не может использоваться для добавления ресурсов в существующий файл. Этот пример проводит путем проверки файла SerializedTimeZones.resx и, если он существует, хранение все ее ресурсы, отличные от двух сериализован часовых поясов в универсальный <xref:System.Collections.Generic.Dictionary%602> объекта. Удаляется существующий файл, и существующие ресурсы добавляются в новый файл SerializedTimeZones.resx. Также сериализованных данных часового пояса добавляется к этому файлу.

Ключ (или **имя**) полей ресурсов не должен содержать пробелы. <xref:System.String.Replace%28System.String%2CSystem.String%29> Вызывается метод, чтобы удалить все внедренные пробелы в идентификаторы часовых поясов, прежде чем они помещаются в файл ресурсов.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы добавить в проект ссылку на System.Windows.Forms.dll и System.Core.dll.

* Что импортируется следующие пространства имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также

* [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
* [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)
* [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
