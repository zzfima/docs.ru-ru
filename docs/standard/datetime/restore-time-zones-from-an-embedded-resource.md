---
title: "Практическое руководство. Восстановление часовых поясов из внедренного ресурса | Microsoft Docs"
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
  - "часовые пояса [платформа .NET Framework], десериализация"
  - "часовые пояса [платформа .NET Framework], восстановление"
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Восстановление часовых поясов из внедренного ресурса
В этом разделе описывается восстановление часовых поясов, которые были сохранены в файле ресурсов.  Сведения и инструкции по сохранению часовых поясов см. в разделе [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).  
  
### Для десериализации объекта TimeZoneInfo из внедренного ресурса  
  
1.  Если извлекаемый часовой пояс не является пользовательским часовым поясом, попытайтесь создать его экземпляр с помощью метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.  
  
2.  Создайте объект <xref:System.Resources.ResourceManager>, передав полное имя файла внедренного ресурса и ссылку на сборку, содержащую файл ресурсов.  
  
     Если вам не удается определить полное имя внедренного ресурсного файла, используйте [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для проверки манифеста сборки.  Элемент `.mresource` идентифицирует ресурс.  В примере полным ресурсным именем является `SerializeTimeZoneData.SerializedTimeZones`.  
  
     Если файл ресурсов внедрен в ту же сборку, которая содержит код экземпляра часового пояса, то можно получить ссылку на него, вызвав метод `static` \(`Shared` в Visual Basic\) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
3.  При сбое вызова метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> или, если необходимо создать пользовательский часовой пояс, можно извлечь строку, содержащую сериализованный часовой пояс, вызвав метод <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>.  
  
4.  Чтобы десериализовать данные часового пояса, вызовите метод <xref:System.TimeZoneInfo.FromSerializedString%2A>.  
  
## Пример  
 В следующем примере десериализуется объект <xref:System.TimeZoneInfo>, хранящийся во внедренном файле ресурсов .NET XML.  
  
 [!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
 [!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]  
  
 Этот код иллюстрирует обработку исключений, чтобы обеспечить присутствие объекта <xref:System.TimeZoneInfo>, необходимого приложению.  Сначала код пробует создать объект <xref:System.TimeZoneInfo>, извлекая его из реестра с помощью метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.  Если часовой пояс не может быть создан, то код извлекает его из внедренного ресурсного файла.  
  
 Так как данные для пользовательских часовых поясов \(часовых поясов, созданных с помощью метода <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\) не хранятся в реестре, код не осуществляет вызов <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для создания часового пояса Антарктики.  Вместо этого код сразу обращается к файлу внедренных ресурсов, чтобы получить строку, содержащую данные пользовательского часового пояса, прежде чем вызывать метод <xref:System.TimeZoneInfo.FromSerializedString%2A>.  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Чтобы ссылки на System.Windows.Forms.dll и System.Core.dll были добавлены в проект.  
  
-   Чтобы был осуществлен импорт следующих пространств имен:  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md)   
 [Практическое руководство. Сохранение часовых поясов во внедренном ресурсе](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)