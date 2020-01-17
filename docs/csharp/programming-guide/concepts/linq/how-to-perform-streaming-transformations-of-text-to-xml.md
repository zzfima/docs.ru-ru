---
title: Выполнение потоковых преобразований текста в XML (C#)
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: 496535b7f868095a62be2b72b1eea2b082e00a44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345794"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a><span data-ttu-id="14769-102">Выполнение потоковых преобразований текста в XML (C#)</span><span class="sxs-lookup"><span data-stu-id="14769-102">How to perform streaming transformations of text to XML (C#)</span></span>

<span data-ttu-id="14769-103">Одним из вариантов обработки текстового файла является написание метода расширения, который обрабатывает текстовый файл построчно при помощи конструкции `yield return`.</span><span class="sxs-lookup"><span data-stu-id="14769-103">One approach to processing a text file is to write an extension method that streams the text file a line at a time using the `yield return` construct.</span></span> <span data-ttu-id="14769-104">Затем можно будет написать запрос LINQ, обрабатывающий текстовый файл в отложенной манере.</span><span class="sxs-lookup"><span data-stu-id="14769-104">You then can write a LINQ query that processes the text file in a lazy deferred fashion.</span></span> <span data-ttu-id="14769-105">При использовании объекта <xref:System.Xml.Linq.XStreamingElement> для формирования выходного потока можно создать преобразование из текстового файла в XML, которое будет использовать минимальный объем памяти независимо от размера исходного текстового файла.</span><span class="sxs-lookup"><span data-stu-id="14769-105">If you then use <xref:System.Xml.Linq.XStreamingElement> to stream output, you then can create a transformation from the text file to XML that uses a minimal amount of memory, regardless of the size of the source text file.</span></span>

 <span data-ttu-id="14769-106">Следует сказать несколько слов о потоковых преобразованиях.</span><span class="sxs-lookup"><span data-stu-id="14769-106">There are some caveats regarding streaming transformations.</span></span> <span data-ttu-id="14769-107">Потоковое преобразование лучше всего применять в ситуациях, когда можно обработать весь файл один раз, а также если можно обработать строки в том порядке, в котором они расположены в исходном документе.</span><span class="sxs-lookup"><span data-stu-id="14769-107">A streaming transformation is best applied in situations where you can process the entire file once, and if you can process the lines in the order that they occur in the source document.</span></span> <span data-ttu-id="14769-108">Если файл требуется обрабатывать более одного раза или необходимо сортировать строки перед обработкой, потоковый метод теряет многие из своих преимуществ.</span><span class="sxs-lookup"><span data-stu-id="14769-108">If you have to process the file more than once, or if you have to sort the lines before you can process them, you will lose many of the benefits of using a streaming technique.</span></span>

## <a name="example"></a><span data-ttu-id="14769-109">Пример</span><span class="sxs-lookup"><span data-stu-id="14769-109">Example</span></span>

 <span data-ttu-id="14769-110">В качестве исходного для этого примера используется текстовый файл People.txt.</span><span class="sxs-lookup"><span data-stu-id="14769-110">The following text file, People.txt, is the source for this example.</span></span>

```text
#This is a comment
1,Tai,Yee,Writer
2,Nikolay,Grachev,Programmer
3,David,Wright,Inventor
```

 <span data-ttu-id="14769-111">Следующий код содержит метод расширения, который обрабатывает строки текстового файла в отложенной манере.</span><span class="sxs-lookup"><span data-stu-id="14769-111">The following code contains an extension method that streams the lines of the text file in a deferred fashion.</span></span>

```csharp
public static class StreamReaderSequence
{
    public static IEnumerable<string> Lines(this StreamReader source)
    {
        if (source == null)
            throw new ArgumentNullException(nameof(source));

        string line;
        while ((line = source.ReadLine()) != null)
        {
            yield return line;
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        var sr = new StreamReader("People.txt");
        var xmlTree = new XStreamingElement("Root",
            from line in sr.Lines()
            let items = line.Split(',')
            where !line.StartsWith("#")
            select new XElement("Person",
                       new XAttribute("ID", items[0]),
                       new XElement("First", items[1]),
                       new XElement("Last", items[2]),
                       new XElement("Occupation", items[3])
                   )
        );
        Console.WriteLine(xmlTree);
        sr.Close();
    }
}
```

 <span data-ttu-id="14769-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="14769-112">This example produces the following output:</span></span>

```xml
<Root>
  <Person ID="1">
    <First>Tai</First>
    <Last>Yee</Last>
    <Occupation>Writer</Occupation>
  </Person>
  <Person ID="2">
    <First>Nikolay</First>
    <Last>Grachev</Last>
    <Occupation>Programmer</Occupation>
  </Person>
  <Person ID="3">
    <First>David</First>
    <Last>Wright</Last>
    <Occupation>Inventor</Occupation>
  </Person>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="14769-113">См. также</span><span class="sxs-lookup"><span data-stu-id="14769-113">See also</span></span>

- <xref:System.Xml.Linq.XStreamingElement>
