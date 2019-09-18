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
ms.openlocfilehash: 32217b9e681179c246560ff5b51b65b4f4e044d5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052885"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="28161-102">dateTimeInvalidLocalFormat MDA</span><span class="sxs-lookup"><span data-stu-id="28161-102">dateTimeInvalidLocalFormat MDA</span></span>
<span data-ttu-id="28161-103">Помощник по отладке управляемого кода `dateTimeInvalidLocalFormat` активируется в том случае, если экземпляр <xref:System.DateTime>, который хранится в формате времени UTC, форматируется с использованием формата, предназначенного только для локальных экземпляров <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="28161-103">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="28161-104">Этот помощник не активируется в том случае, если экземпляры <xref:System.DateTime> не заданы или заданы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28161-104">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="28161-105">Симптом</span><span class="sxs-lookup"><span data-stu-id="28161-105">Symptom</span></span>  
 <span data-ttu-id="28161-106">Приложение вручную сериализует экземпляр <xref:System.DateTime> в формате UTC с использованием локального формата:</span><span class="sxs-lookup"><span data-stu-id="28161-106">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="28161-107">Причина</span><span class="sxs-lookup"><span data-stu-id="28161-107">Cause</span></span>  
 <span data-ttu-id="28161-108">Формат "z" для метода <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> включает сдвиг местного часового пояса, например "+03:00" для московского времени.</span><span class="sxs-lookup"><span data-stu-id="28161-108">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="28161-109">Таким образом, значащий результат будет получен только в том случае, если экземпляр <xref:System.DateTime> содержит значение местного времени.</span><span class="sxs-lookup"><span data-stu-id="28161-109">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="28161-110">Если время указано в формате UTC, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> содержит сдвиг местного часового пояса, однако не отображает и не позволяет изменять описатель часового пояса.</span><span class="sxs-lookup"><span data-stu-id="28161-110">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="28161-111">Решение</span><span class="sxs-lookup"><span data-stu-id="28161-111">Resolution</span></span>  
 <span data-ttu-id="28161-112">Экземпляры <xref:System.DateTime> в формате UTC должны иметь форматирование, явно указывающее на это.</span><span class="sxs-lookup"><span data-stu-id="28161-112">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="28161-113">Для работы со временем в формате UTC рекомендуется использовать формат "Z":</span><span class="sxs-lookup"><span data-stu-id="28161-113">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="28161-114">Также доступен формат "o", который сериализует <xref:System.DateTime> с использованием свойства <xref:System.DateTime.Kind%2A> и обеспечивает корректную сериализацию независимо от того, содержит экземпляр местное время, время в формате UTC или формат не указан:</span><span class="sxs-lookup"><span data-stu-id="28161-114">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="28161-115">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="28161-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="28161-116">Этот помощник по отладке управляемого кода не влияет на среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="28161-116">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="28161-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="28161-117">Output</span></span>  
 <span data-ttu-id="28161-118">В результате его активации не возвращаются какие-либо конкретные выходные данные. Тем не менее с помощью стека вызовов можно определить расположение вызова <xref:System.DateTime.ToString%2A>, который стал причиной активации этого помощника.</span><span class="sxs-lookup"><span data-stu-id="28161-118">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="28161-119">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="28161-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="28161-120">Пример</span><span class="sxs-lookup"><span data-stu-id="28161-120">Example</span></span>  
 <span data-ttu-id="28161-121">Рассмотрите возможность косвенной сериализации значений <xref:System.DateTime> в формате UTC с использованием класса <xref:System.Xml.XmlConvert> или <xref:System.Data.DataSet>, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="28161-121">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="28161-122">В сериализациях <xref:System.Xml.XmlConvert> и <xref:System.Data.DataSet> по умолчанию используется локальный формат.</span><span class="sxs-lookup"><span data-stu-id="28161-122">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="28161-123">Для сериализации значений <xref:System.DateTime> другого вида, например в формате UTC, требуется указать дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="28161-123">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="28161-124">Конкретно в этом примере необходимо передать `XmlDateTimeSerializationMode.RoundtripKind` в вызов `ToString` для `XmlConvert`.</span><span class="sxs-lookup"><span data-stu-id="28161-124">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="28161-125">В этом случае данные сериализуются как время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="28161-125">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="28161-126">При использовании <xref:System.Data.DataSet> присвойте свойству <xref:System.Data.DataColumn.DateTimeMode%2A> объекта <xref:System.Data.DataColumn> значение <xref:System.Data.DataSetDateTime.Utc>.</span><span class="sxs-lookup"><span data-stu-id="28161-126">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="28161-127">См. также</span><span class="sxs-lookup"><span data-stu-id="28161-127">See also</span></span>

- <xref:System.Globalization.DateTimeFormatInfo>
- [<span data-ttu-id="28161-128">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="28161-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
