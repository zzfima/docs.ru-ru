---
title: "Преобразование строк в типы данных .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="19c83-102">Преобразование строк в типы данных .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19c83-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="19c83-103">Если вы хотите преобразовать строку в тип данных .NET Framework, используйте **XmlConvert** метод, соответствующий требованиям приложения.</span><span class="sxs-lookup"><span data-stu-id="19c83-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="19c83-104">Список всех методов преобразования в **XmlConvert** см. в описании <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="19c83-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="19c83-105">Строка, возвращаемая из **ToString** метод — это строковая версия, переданного в данных.</span><span class="sxs-lookup"><span data-stu-id="19c83-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="19c83-106">Кроме того, существует несколько типов .NET Framework, которые преобразуются с помощью **XmlConvert** класса, но они не используют методы в **System.Convert** класса.</span><span class="sxs-lookup"><span data-stu-id="19c83-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="19c83-107">**XmlConvert** класс соответствует спецификации типа данных схемы XML (XSD) и имеет тип данных, **XmlConvert** может быть сопоставлен.</span><span class="sxs-lookup"><span data-stu-id="19c83-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="19c83-108">В следующей таблице перечислены типы данных .NET Framework и строковые типы, возвращаемые с помощью сопоставления типа данных XSD.</span><span class="sxs-lookup"><span data-stu-id="19c83-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="19c83-109">Эти типы .NET Framework не может обрабатываться с помощью **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="19c83-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="19c83-110">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19c83-110">.NET Framework type</span></span>|<span data-ttu-id="19c83-111">Возвращаемая строка</span><span class="sxs-lookup"><span data-stu-id="19c83-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="19c83-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="19c83-112">Boolean</span></span>|<span data-ttu-id="19c83-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="19c83-113">"true", "false"</span></span>|  
|<span data-ttu-id="19c83-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="19c83-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-115">"INF"</span></span>|  
|<span data-ttu-id="19c83-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="19c83-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-117">"-INF"</span></span>|  
|<span data-ttu-id="19c83-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="19c83-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-119">"INF"</span></span>|  
|<span data-ttu-id="19c83-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="19c83-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-121">"-INF"</span></span>|  
|<span data-ttu-id="19c83-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="19c83-122">DateTime</span></span>|<span data-ttu-id="19c83-123">Используется формат «гггг-ММ-ддТЧЧ:мм:ссzzzzzz» и его сокращенные версии.</span><span class="sxs-lookup"><span data-stu-id="19c83-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="19c83-124">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="19c83-124">Timespan</span></span>|<span data-ttu-id="19c83-125">Используется формат PnYnMnTnHnMnS, то есть значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="19c83-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="19c83-126">Если преобразование любого типа .NET Framework, перечисленных в таблице в строку с помощью **ToString** метод, возвращаемая строка не является базовым типом, но строковый тип схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="19c83-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="19c83-127">**DateTime** и **Timespan** тип значения отличаются тем, что **DateTime** представляет момент времени, а **TimeSpan** представляет интервал времени.</span><span class="sxs-lookup"><span data-stu-id="19c83-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="19c83-128">**DateTime** и **Timespan** форматы указаны в спецификации типов данных схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="19c83-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="19c83-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="19c83-129">For example:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 <span data-ttu-id="19c83-130">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="19c83-130">**Output**</span></span>  
  
 <span data-ttu-id="19c83-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="19c83-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="19c83-132">В следующем примере кода целочисленное значение преобразуется в строку.</span><span class="sxs-lookup"><span data-stu-id="19c83-132">The following code converts an integer to a string:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 <span data-ttu-id="19c83-133">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="19c83-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="19c83-134">Тем не менее при преобразовании строки **логическое**, **один**, или **двойные**, возвращаемый тип .NET Framework не совпадает с типом, возвращаемым при использовании **System.Convert** класса.</span><span class="sxs-lookup"><span data-stu-id="19c83-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="19c83-135">Преобразование строки в тип Boolean</span><span class="sxs-lookup"><span data-stu-id="19c83-135">String to Boolean</span></span>  
 <span data-ttu-id="19c83-136">Следующая таблица показывает, какие типы создаются для заданных входных строк при преобразовании строки в **логическое** с помощью **ToBoolean** метод.</span><span class="sxs-lookup"><span data-stu-id="19c83-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="19c83-137">Допустимый строковый входной параметр</span><span class="sxs-lookup"><span data-stu-id="19c83-137">Valid string input parameter</span></span>|<span data-ttu-id="19c83-138">Выходной тип .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19c83-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="19c83-139">"true"</span><span class="sxs-lookup"><span data-stu-id="19c83-139">"true"</span></span>|<span data-ttu-id="19c83-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="19c83-140">Boolean.True</span></span>|  
|<span data-ttu-id="19c83-141">"1"</span><span class="sxs-lookup"><span data-stu-id="19c83-141">"1"</span></span>|<span data-ttu-id="19c83-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="19c83-142">Boolean.True</span></span>|  
|<span data-ttu-id="19c83-143">"false"</span><span class="sxs-lookup"><span data-stu-id="19c83-143">"false"</span></span>|<span data-ttu-id="19c83-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="19c83-144">Boolean.False</span></span>|  
|<span data-ttu-id="19c83-145">"0"</span><span class="sxs-lookup"><span data-stu-id="19c83-145">"0"</span></span>|<span data-ttu-id="19c83-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="19c83-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="19c83-147">Например, пусть задан следующий XML-код.</span><span class="sxs-lookup"><span data-stu-id="19c83-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="19c83-148">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="19c83-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 <span data-ttu-id="19c83-149">Можно воспринимать как в следующем примере кода и **bvalue** — **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="19c83-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="19c83-150">Преобразование строки в тип Single</span><span class="sxs-lookup"><span data-stu-id="19c83-150">String to Single</span></span>  
 <span data-ttu-id="19c83-151">Следующая таблица показывает, какие типы создаются для заданных входных строк при преобразовании строки в **один** с помощью **ToSingle** метод.</span><span class="sxs-lookup"><span data-stu-id="19c83-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="19c83-152">Допустимый строковый входной параметр</span><span class="sxs-lookup"><span data-stu-id="19c83-152">Valid string input parameter</span></span>|<span data-ttu-id="19c83-153">Выходной тип .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19c83-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="19c83-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-154">"INF"</span></span>|<span data-ttu-id="19c83-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="19c83-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-156">"-INF"</span></span>|<span data-ttu-id="19c83-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="19c83-158">Преобразование строки в тип Double</span><span class="sxs-lookup"><span data-stu-id="19c83-158">String to Double</span></span>  
 <span data-ttu-id="19c83-159">Следующая таблица показывает, какие типы создаются для заданных входных строк при преобразовании строки в **один** с помощью **ToDouble** метод.</span><span class="sxs-lookup"><span data-stu-id="19c83-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="19c83-160">Допустимый строковый входной параметр</span><span class="sxs-lookup"><span data-stu-id="19c83-160">Valid string input parameter</span></span>|<span data-ttu-id="19c83-161">Выходной тип .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19c83-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="19c83-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-162">"INF"</span></span>|<span data-ttu-id="19c83-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="19c83-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="19c83-164">"-INF"</span></span>|<span data-ttu-id="19c83-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="19c83-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="19c83-166">Следующий код записывает строку `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="19c83-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="19c83-167">См. также</span><span class="sxs-lookup"><span data-stu-id="19c83-167">See Also</span></span>  
 [<span data-ttu-id="19c83-168">Преобразование типов данных XML</span><span class="sxs-lookup"><span data-stu-id="19c83-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="19c83-169">Преобразование типов .NET Framework в строки</span><span class="sxs-lookup"><span data-stu-id="19c83-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
