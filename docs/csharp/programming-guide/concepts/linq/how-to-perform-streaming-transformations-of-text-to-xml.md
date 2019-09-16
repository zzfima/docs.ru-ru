---
title: Практическое руководство. Выполнение потоковых преобразований текста в XML (C#)
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: 6dc48a7342bbeedb79e8e7f4a9270899be336f91
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851034"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a>Практическое руководство. Выполнение потоковых преобразований текста в XML (C#)

Одним из вариантов обработки текстового файла является написание метода расширения, который обрабатывает текстовый файл построчно при помощи конструкции `yield return`. Затем можно будет написать запрос LINQ, обрабатывающий текстовый файл в отложенной манере. При использовании объекта <xref:System.Xml.Linq.XStreamingElement> для формирования выходного потока можно создать преобразование из текстового файла в XML, которое будет использовать минимальный объем памяти независимо от размера исходного текстового файла.

 Следует сказать несколько слов о потоковых преобразованиях. Потоковое преобразование лучше всего применять в ситуациях, когда можно обработать весь файл один раз, а также если можно обработать строки в том порядке, в котором они расположены в исходном документе. Если файл требуется обрабатывать более одного раза или необходимо сортировать строки перед обработкой, потоковый метод теряет многие из своих преимуществ.

## <a name="example"></a>Пример

 В качестве исходного для этого примера используется текстовый файл People.txt.

```text
#This is a comment
1,Tai,Yee,Writer
2,Nikolay,Grachev,Programmer
3,David,Wright,Inventor
```

 Следующий код содержит метод расширения, который обрабатывает строки текстового файла в отложенной манере.

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

 В этом примере выводятся следующие данные:

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

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XStreamingElement>
