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
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Как: сохранение часовых поясов во внедренном ресурсе

Часовому поясу приложение часто требуется наличие определенного часового пояса. Тем не менее поскольку доступность отдельных <xref:System.TimeZoneInfo> объектов зависит от сведений, хранящихся в локальном реестре пользователя, даже настраиваемые доступные часовые пояса могут отсутствовать. Кроме того, сведения о настраиваемых часовых поясов, созданных с помощью <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода не сохраняется вместе с другими данными часового пояса в реестре. Убедитесь, что доступны этих часовых поясах, при необходимости, можно сохранить их можно сериализовать и последующее восстановление их десериализовать.

Обычно сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения часовыми поясами. В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, данные о часовом поясе может быть сериализован в рамках процедуры установки или настройки (например, если данные хранятся в ключе реестра), или как часть служебной процедуры, запускаемой Перед окончательной компиляцией приложения (например, когда сериализованные данные хранятся в файле ресурсов (RESX) .NET XML).

Помимо файла ресурсов, который компилируется с приложением можно использовать несколько хранилищ данных, информации о часовых поясах. В число этих требований входят следующие:

* Реестр. Обратите внимание, что приложение должно использовать подразделов раздела свои собственные приложения для хранения данных пользовательского часового пояса, а не с помощью подразделов параметру NT\CurrentVersion\Time зон.

* Файлы конфигурации.

* Другие системные файлы.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Для сохранения часового пояса путем сериализации его в RESX-файла

1. Извлечь существующий часовой пояс или создайте новый часовой пояс.

   Для получения существующий часовой пояс, [как: доступ к предопределенные объекты пояса UTC и местным временем](../../../docs/standard/datetime/access-utc-and-local.md) и [как: создание объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Чтобы создать новый часовой пояс, вызовите одну из перегрузок <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метод. Дополнительные сведения см. в разделе [как: создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) и [как: создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Вызовите <xref:System.TimeZoneInfo.ToSerializedString%2A> метод, чтобы создать строку, содержащую данные о часовом поясе.

3. Создать экземпляр <xref:System.IO.StreamWriter> , указав имя и при необходимости путь RESX-файл для <xref:System.IO.StreamWriter> конструктора класса.

4. Создать экземпляр <xref:System.Resources.ResXResourceWriter> путем передачи <xref:System.IO.StreamWriter> объект <xref:System.Resources.ResXResourceWriter> конструктора класса.

5. Передайте часового пояса в сериализованную строку для <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> метод.

6. Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Закрыть <xref:System.IO.StreamWriter> , вызывая его <xref:System.IO.StreamWriter.Close%2A> метод.

9. Добавьте созданный RESX-файл в проект Visual Studio для приложения.

10. С помощью **свойства** в Visual Studio, убедитесь, что в RESX-файл **действие при построении** свойству **внедренный ресурс**.

## <a name="example"></a>Пример

В следующем примере сериализуется <xref:System.TimeZoneInfo> , представляющий центральное стандартное время и <xref:System.TimeZoneInfo> объект, представляющий антарктическое время, сериализуются в файл ресурсов .NET XML, который называется SerializedTimeZones.resx. Центральное стандартное время, обычно определяются в реестре; Антарктическое является пользовательский часовой пояс.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

В этом примере выполняется сериализация <xref:System.TimeZoneInfo> объектов, чтобы они были доступны в файле ресурсов во время компиляции.

Поскольку <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> метод добавляет полные сведения заголовка в файл ресурсов .NET XML, не может использоваться для добавления ресурсов в существующий файл. Этот пример проводит путем проверки файла SerializedTimeZones.resx и, если он существует, отличный от его ресурсы хранения этих двух сериализованных часовых поясов в универсальный тип <xref:System.Collections.Generic.Dictionary%602> объекта. Существующий файл удаляется, а существующие ресурсы добавляются в новый файл SerializedTimeZones.resx. Сериализованные данные часового пояса также добавляется в этот файл.

Ключ (или **имя**) полей ресурсов не должен содержать пробелы. <xref:System.String.Replace%28System.String%2CSystem.String%29> Метод вызывается для удаления всех пробелов в идентификаторы часовых поясов, прежде чем они помещаются в файл ресурсов.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

* Чтобы ссылка System.Windows.Forms.dll и System.Core.dll была добавлена в проект.

* Что импортируется следующие пространства имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md)
[как: восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
