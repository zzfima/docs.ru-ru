---
title: Как сохранять Часовые пояса во внедренном ресурсе
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
ms.openlocfilehash: aaee4e82d09e8b604d06dadb5a5eefe8d2e1f307
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123771"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Как сохранять Часовые пояса во внедренном ресурсе

Для приложения, поддерживающего Часовые пояса, часто требуется наличие определенного часового пояса. Однако, поскольку доступность отдельных объектов <xref:System.TimeZoneInfo> зависит от информации, хранящейся в реестре локальной системы, даже нестандартно доступные часовые пояса могут отсутствовать. Кроме того, сведения о настраиваемых часовых поясах, создаваемых с помощью метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>, не сохраняются с другими сведениями о часовом поясе в реестре. Чтобы обеспечить доступность этих часовых поясов при необходимости, их можно сохранить путем их сериализации и последующего восстановления путем их десериализации.

Как правило, сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения, поддерживающего часовой пояс. В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, данные часового пояса могут быть сериализованы как часть программы установки или установки (например, когда данные хранятся в реестре) или как часть служебной программы, выполняемой до окончательное приложение компилируется (например, если сериализованные данные хранятся в файле ресурсов XML .NET (RESX)).

Помимо файла ресурсов, компилируемого с приложением, для сведений о часовом поясе можно использовать несколько других хранилищ данных. В число этих требований входят следующие:

- Реестр. Обратите внимание, что приложение должно использовать подразделы собственного ключа приложения для хранения пользовательских данных часового пояса, а не использовать подразделы зон HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Nt\currentversion\time Zones.

- Файлы конфигурации.

- Другие системные файлы.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Сохранение часового пояса путем его сериализации в RESX-файл

1. Получение существующего часового пояса или создание нового часового пояса.

   Чтобы получить существующий часовой пояс, см. раздел [как получить доступ к стандартным объектам времени в формате UTC и местному часовому поясу](../../../docs/standard/datetime/access-utc-and-local.md) и [как создать объект TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Чтобы создать новый часовой пояс, вызовите одну из перегрузок метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Дополнительные сведения см. в статьях [как создавать Часовые пояса без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) и [как создавать Часовые пояса с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Вызовите метод <xref:System.TimeZoneInfo.ToSerializedString%2A>, чтобы создать строку, содержащую данные часового пояса.

3. Создайте экземпляр объекта <xref:System.IO.StreamWriter>, указав имя и, при необходимости, путь к RESX-файлу в конструктор класса <xref:System.IO.StreamWriter>.

4. Создайте экземпляр объекта <xref:System.Resources.ResXResourceWriter>, передав <xref:System.IO.StreamWriter> объект в конструктор класса <xref:System.Resources.ResXResourceWriter>.

5. Передайте сериализованную строку часового пояса в метод <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType>.

6. Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Закройте объект <xref:System.IO.StreamWriter>, вызвав его метод <xref:System.IO.StreamWriter.Close%2A>.

9. Добавьте созданный RESX файл в проект приложения Visual Studio.

10. С помощью окна **Свойства** в Visual Studio убедитесь, что для свойства **действие сборки** RESX-файла задано значение **внедренный ресурс**.

## <a name="example"></a>Пример

В следующем примере сериализуется объект <xref:System.TimeZoneInfo>, представляющий центральное стандартное время и объект <xref:System.TimeZoneInfo>, представляющий станцию Палмер, время Антарктида в файл ресурсов XML .NET с именем Сериализедтимезонес. resx. Центральное стандартное время обычно определяется в реестре; Палмер станция, Антарктида — настраиваемый часовой пояс.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

В этом примере сериализуется <xref:System.TimeZoneInfo> объекты, чтобы они были доступны в файле ресурсов во время компиляции.

Поскольку метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> добавляет полные данные заголовка в файл ресурсов XML .NET, он не может использоваться для добавления ресурсов в существующий файл. Этот пример обрабатывает это путем проверки файла Сериализедтимезонес. resx и (если он существует), сохраняя все ресурсы, кроме двух сериализованных часовых поясов, в универсальный объект <xref:System.Collections.Generic.Dictionary%602>. После этого существующий файл удаляется, а существующие ресурсы добавляются в новый файл Сериализедтимезонес. resx. Сериализованные данные часового пояса также добавляются в этот файл.

Поля ключа (или **имени**) ресурсов не должны содержать пробелы. Метод <xref:System.String.Replace%28System.String%2CSystem.String%29> вызывается для удаления всех внедренных пробелов в идентификаторах часовых поясов до их назначения в файл ресурсов.

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- Ссылка на библиотеку System. Windows. Forms. dll и System. Core. dll будет добавлена в проект.

- Для импорта следующих пространств имен:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>См. также

- [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
- [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)
- [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
