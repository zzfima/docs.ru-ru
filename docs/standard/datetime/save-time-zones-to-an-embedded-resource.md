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
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Практическое руководство. Сохранение часовых поясов во внедренном ресурсе

Для приложения, поддерживающего Часовые пояса, часто требуется наличие определенного часового пояса. Однако, поскольку доступность отдельных <xref:System.TimeZoneInfo> объектов зависит от информации, хранящейся в реестре локальной системы, даже нестандартно доступные часовые пояса могут отсутствовать. Кроме того <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> , сведения о настраиваемых часовых поясах, создаваемых с помощью метода, не сохраняются с другими сведениями о часовом поясе в реестре. Чтобы обеспечить доступность этих часовых поясов при необходимости, их можно сохранить путем их сериализации и последующего восстановления путем их десериализации.

Как правило, сериализация <xref:System.TimeZoneInfo> объекта происходит отдельно от приложения, поддерживающего часовой пояс. В зависимости от хранилища данных, используемого для хранения сериализованных <xref:System.TimeZoneInfo> объектов, данные часового пояса могут быть сериализованы как часть программы установки или установки (например, когда данные хранятся в реестре) или в составе служебной программы, выполняемой перед компиляцией окончательного приложения (например, если сериализованные данные хранятся в файле ресурсов XML .NET (RESX)).

Помимо файла ресурсов, компилируемого с приложением, для сведений о часовом поясе можно использовать несколько других хранилищ данных. следующие основные параметры.

- Реестр. Обратите внимание, что приложение должно использовать подразделы собственного ключа приложения для хранения пользовательских данных часового пояса, а не использовать подразделы зон HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Nt\currentversion\time Zones.

- Файлы конфигурации.

- Другие системные файлы.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Сохранение часового пояса путем его сериализации в RESX-файл

1. Получение существующего часового пояса или создание нового часового пояса.

   Чтобы получить существующий часовой пояс, см. [раздел как Доступ к стандартным объектам](../../../docs/standard/datetime/access-utc-and-local.md) времени в формате UTC и местному часовому поясу, а [также: Создайте экземпляр объекта](../../../docs/standard/datetime/instantiate-time-zone-info.md)TimeZoneInfo.

   Чтобы создать новый часовой пояс, вызовите одну из перегрузок <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> метода. Дополнительные сведения см. в разделе [Практическое руководство. Создавайте Часовые пояса без](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) правил [коррекции и выполняя следующие действия: Создание часовых поясов с правилами](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)коррекции.

2. Вызовите <xref:System.TimeZoneInfo.ToSerializedString%2A> метод, чтобы создать строку, содержащую данные часового пояса.

3. Создайте экземпляр <xref:System.IO.StreamWriter> объекта, указав имя и, при необходимости, путь к RESX-файлу конструктора класса. <xref:System.IO.StreamWriter>

4. Создайте экземпляр <xref:System.IO.StreamWriter>объекта, передав объект в <xref:System.Resources.ResXResourceWriter> конструктор класса. <xref:System.Resources.ResXResourceWriter>

5. Передайте сериализованную строку часового пояса в <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> метод.

6. Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Закройте объект, вызвав его <xref:System.IO.StreamWriter.Close%2A>метод. <xref:System.IO.StreamWriter>

9. Добавьте созданный RESX файл в проект приложения Visual Studio.

10. С помощью окна **Свойства** в Visual Studio убедитесь, что для свойства **действие сборки** RESX-файла задано значение Внедренный **ресурс**.

## <a name="example"></a>Пример

В следующем примере сериализуется <xref:System.TimeZoneInfo> объект, представляющий центральное стандартное время, <xref:System.TimeZoneInfo> и объект, представляющий Палмер станцию, Антарктида время в файл ресурсов .NET XML с именем сериализедтимезонес. resx. Центральное стандартное время обычно определяется в реестре; Палмер станция, Антарктида — настраиваемый часовой пояс.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

В этом примере сериализуются <xref:System.TimeZoneInfo> объекты, чтобы они были доступны в файле ресурсов во время компиляции.

<xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> Поскольку метод добавляет полные данные заголовка в файл ресурсов XML .NET, он не может использоваться для добавления ресурсов в существующий файл. Этот пример обрабатывает это путем проверки файла сериализедтимезонес. resx и (если он существует), сохраняя все ресурсы, кроме двух сериализованных часовых поясов, в универсальный <xref:System.Collections.Generic.Dictionary%602> объект. После этого существующий файл удаляется, а существующие ресурсы добавляются в новый файл Сериализедтимезонес. resx. Сериализованные данные часового пояса также добавляются в этот файл.

Поля ключа (или **имени**) ресурсов не должны содержать пробелы. <xref:System.String.Replace%28System.String%2CSystem.String%29> Метод вызывается для удаления всех внедренных пробелов в идентификаторах часовых поясов до их назначения в файл ресурсов.

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
