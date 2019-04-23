---
title: dateTimeInvalidLocalFormat MDA
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 380334dbe9b91ea369de6cbe58686a9a74254c2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148230"
---
# <a name="datetimeinvalidlocalformat-mda"></a>dateTimeInvalidLocalFormat MDA
Помощник по отладке управляемого кода `dateTimeInvalidLocalFormat` активируется в том случае, если экземпляр <xref:System.DateTime>, который хранится в формате времени UTC, форматируется с использованием формата, предназначенного только для локальных экземпляров <xref:System.DateTime>. Этот помощник не активируется в том случае, если экземпляры <xref:System.DateTime> не заданы или заданы по умолчанию.  
  
## <a name="symptom"></a>Симптом  
 Приложение вручную сериализует экземпляр <xref:System.DateTime> в формате UTC с использованием локального формата:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a>Причина  
 Формат "z" для метода <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> включает сдвиг местного часового пояса, например "+03:00" для московского времени. Таким образом, значащий результат будет получен только в том случае, если экземпляр <xref:System.DateTime> содержит значение местного времени. Если время указано в формате UTC, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> содержит сдвиг местного часового пояса, однако не отображает и не позволяет изменять описатель часового пояса.  
  
### <a name="resolution"></a>Решение  
 Экземпляры <xref:System.DateTime> в формате UTC должны иметь форматирование, явно указывающее на это. Для работы со временем в формате UTC рекомендуется использовать формат "Z":  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 Также доступен формат "o", который сериализует <xref:System.DateTime> с использованием свойства <xref:System.DateTime.Kind%2A> и обеспечивает корректную сериализацию независимо от того, содержит экземпляр местное время, время в формате UTC или формат не указан:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник по отладке управляемого кода не влияет на среду выполнения.  
  
## <a name="output"></a>Вывод  
 В результате его активации не возвращаются какие-либо конкретные выходные данные. Тем не менее с помощью стека вызовов можно определить расположение вызова <xref:System.DateTime.ToString%2A>, который стал причиной активации этого помощника.  
  
## <a name="configuration"></a>Параметр Configuration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 Рассмотрите возможность косвенной сериализации значений <xref:System.DateTime> в формате UTC с использованием класса <xref:System.Xml.XmlConvert> или <xref:System.Data.DataSet>, как показано ниже.  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 В сериализациях <xref:System.Xml.XmlConvert> и <xref:System.Data.DataSet> по умолчанию используется локальный формат. Для сериализации значений <xref:System.DateTime> другого вида, например в формате UTC, требуется указать дополнительные параметры.  
  
 Конкретно в этом примере необходимо передать `XmlDateTimeSerializationMode.RoundtripKind` в вызов `ToString` для `XmlConvert`. В этом случае данные сериализуются как время в формате UTC.  
  
 При использовании <xref:System.Data.DataSet> присвойте свойству <xref:System.Data.DataColumn.DateTimeMode%2A> объекта <xref:System.Data.DataColumn> значение <xref:System.Data.DataSetDateTime.Utc>.  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization.DateTimeFormatInfo>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
