---
title: "Практическое руководство. Сохранение часовых поясов во внедренном ресурсе | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "объекты часовых поясов [платформа .NET Framework], сохранение"
  - "объекты часовых поясов [платформа .NET Framework], сериализация"
  - "часовые пояса [платформа .NET Framework], сохранение"
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Сохранение часовых поясов во внедренном ресурсе
Часто приложению, работающему со временем, требуется наличие определенного часового пояса.  Однако поскольку доступность отдельных объектов <xref:System.TimeZoneInfo> зависит от сведений, хранящихся в локальном реестре пользователя, даже настраиваемые доступные часовые пояса могут отсутствовать.  Кроме того, сведения о пользовательских часовых поясах, созданных с помощью метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>, не хранятся с другими сведениями о часовом поясе в реестре.  Чтобы гарантировать, что эти часовые пояса будут доступны, когда потребуется, их можно сериализовать и сохранить, а позже десериализовать и восстановить.  
  
 Обычно сериализация объекта <xref:System.TimeZoneInfo> происходит отдельно от приложения, соответствующего часовому поясу.  В зависимости от хранилища данных, используемого для хранения сериализованных объектов <xref:System.TimeZoneInfo>, данные о часовых поясах можно сериализовывать в процессе установки \(например, при сохранении данных в ключе реестра\), или как часть служебной процедуры, запускаемой перед окончательной компиляцией приложения \(например, когда сериализованные данные хранятся в файле ресурсов \(.resX\) .NET XML\).  
  
 В дополнение к файлу ресурсов, который компилируется с приложением, для хранения сведений о часовом поясе могут использоваться некоторые другие хранилища.  Ниже перечислены некоторые из них:  
  
-   Реестр.  Обратите внимание, что для хранения пользовательских данных о часовом поясе приложение должно использовать вложенные разделы своего собственного реестра приложения вместо использования подразделов HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones.  
  
-   Файлы конфигурации.  
  
-   Другие системные файлы.  
  
### Для сохранения часового пояса путем сериализации его в файле .resx  
  
1.  Извлеките существующий часовой пояс или создайте новый часовой пояс.  
  
     Сведения об извлечении текущего часового пояса см. в разделах [Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов](../../../docs/standard/datetime/access-utc-and-local.md) и [Практическое руководство. Создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).  
  
     Чтобы создать новый часовой пояс, вызовите один из вариантов перегруженного метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>.  Дополнительные сведения см. в разделах [Практическое руководство. Создание часовых поясов без правил коррекции](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) и [Практическое руководство. Создание часовых поясов с правилами коррекции](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  
  
2.  Вызовите метод <xref:System.TimeZoneInfo.ToSerializedString%2A> для создания строки, содержащей данные часового пояса.  
  
3.  Создайте объект <xref:System.IO.StreamWriter>, передав имя и при необходимости путь к файлу .resx в конструктор класса <xref:System.IO.StreamWriter>.  
  
4.  Создайте объект <xref:System.Resources.ResXResourceWriter> путем передачи объекта <xref:System.IO.StreamWriter> в конструктор класса <xref:System.Resources.ResXResourceWriter>.  
  
5.  Передайте сериализованную строку часового пояса в метод <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=fullName>.  
  
6.  Вызовите метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName>.  
  
7.  Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=fullName>.  
  
8.  Закройте объект <xref:System.IO.StreamWriter> путем вызова его метода <xref:System.IO.StreamWriter.Close%2A>.  
  
9. Добавьте созданный файл .resx в проект приложения Visual Studio.  
  
10. С помощью окна **Свойства** в Visual Studio, убедитесь, что свойство **Действия при построении** этого файла .resx задано как **Внедренный ресурс**.  
  
## Пример  
 В следующем примере объект <xref:System.TimeZoneInfo>, представляющий центральное стандартное время и объект <xref:System.TimeZoneInfo>, представляющий антарктическое время, сериализуются в файле .NET XML ресурсов под именем SerializedTimeZones.resx.  Центральное стандартное время обычно определено в реестре; антарктическое время является пользовательским часовым поясом.  
  
 [!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
 [!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]  
  
 Этот пример сериализует объекты <xref:System.TimeZoneInfo> таким образом, что они становятся доступными в файле ресурсов во время компиляции.  
  
 Поскольку метод <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName> добавляет полные сведения заголовка в файл ресурсов .NET XML, то он не может использоваться для добавления ресурсов в существующий файл.  Этот пример проводит обработку путем проверки файла SerializedTimeZones.resx и, если он существует, сохранения всех его ресурсов, отличных от этих двух сериализованных часовых поясов в универсальный объект <xref:System.Collections.Generic.Dictionary%602>.  Затем существующий файл удаляется, и существующие ресурсы добавляются в новый файл SerializedTimeZones.resx.  Сериализованные данные часового пояса также добавляются в этот файл.  
  
 Ключ \(или **Имя**\) полей ресурсов не должен содержать пробелы.  Метод <xref:System.String.Replace%28System.String%2CSystem.String%29> вызывается для удаления всех пробелов в идентификаторах часовых поясов, прежде чем они помещаются в файл ресурсов.  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Чтобы ссылки на System.Windows.Forms.dll и System.Core.dll были добавлены в проект.  
  
-   Чтобы был осуществлен импорт следующих пространств имен:  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)   
 [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)