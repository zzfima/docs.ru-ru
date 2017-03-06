---
title: "Практическое руководство. Извлечение протокола и номера порта из URL-адреса"
description: "Практическое руководство. Извлечение протокола и номера порта из URL-адреса"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d2462fb4-6d61-44ab-8466-73f1f06c3058
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 578b70412e876001f4462e2409739acf3609097b
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Практическое руководство. Извлечение протокола и номера порта из URL-адреса

В следующем примере выполняется извлечение протокола и номера порта из URL-адреса. 

## <a name="example"></a>Пример

В примере используется метод [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) для возврата протокола, за которым через двоеточие следует номер порта. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string url = "http://www.contoso.com:8080/letters/readme";

      Regex r = new Regex(@"^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/",
                          RegexOptions.None, TimeSpan.FromMilliseconds(150));
      Match m = r.Match(url);
      if (m.Success)
         Console.WriteLine(r.Match(url).Result("${proto}${port}")); 
   }
}
// The example displays the following output:
//       http:8080
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim url As String = "http://www.contoso.com:8080/letters/readme.html" 
      Dim r As New Regex("^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/",
                         RegexOptions.None, TimeSpan.FromMilliseconds(150))

      Dim m As Match = r.Match(url)
      If m.Success Then
         Console.WriteLine(r.Match(url).Result("${proto}${port}"))
      End If   
   End Sub
End Module
' The example displays the following output:
'       http:8080
```

Возможные интерпретации шаблона регулярного выражения `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` показаны в следующей таблице.

Шаблон | Описание
------- | ----------- 
`^` | Соответствие должно обнаруживаться в начале строки.
`(?<proto>\w+)` | Совпадение с одним или несколькими символами слова. Имя этой группы — proto.
`://` | Совпадение с двоеточием, за которым следуют две косые черты.
`[^/]+?` | Совпадение с одним или несколькими вхождениями (но как можно меньшему числу) любого символа, отличного от косой черты.
`(?<port>:\d+)?` | Совпадение с вхождениями в количестве&0; или&1; двоеточия, за которым следует одна или несколько цифр. Имя этой группы — port.
`/` | Совпадение с косой чертой.
 
Метод [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) разворачивает последовательность замены `${proto}${port}`, которая объединяет захваченное значение двух именованных групп в шаблон регулярного выражения. Это удобная альтернатива явному объединению строк, извлеченных из объекта коллекции, который был возвращен свойством [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups).

В примере используется метод [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) с двумя подстановками `${proto}` и `${port}` для включения захваченных групп в выходную строку. Вместо этого можно извлечь захваченные группы из соответствующего объекта [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), как показано в следующем примере кода.

```csharp
Console.WriteLine(m.Groups["proto"].Value + m.Groups["port"].Value); 
```

```vb
Console.WriteLine(m.Groups("proto").Value + m.Groups("port").Value)
```

## <a name="see-also"></a>См. также

[Регулярные выражения .NET](regular-expressions.md)

[Примеры регулярных выражений](regex-examples.md)

