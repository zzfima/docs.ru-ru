---
title: Практическое руководство. Выполнение запроса к метаданным сборки при помощи отражения (LINQ)
ms.date: 07/20/2015
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
ms.openlocfilehash: 5cc525c6e60efd7cf34f9894b2cbb9389fd0b6ae
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347728"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-visual-basic"></a>How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)
В следующем примере показано использование LINQ с отражением для извлечения определенных метаданных о методах, соответствующих условиям поиска. В этом примере запрос будет искать имена всех методов в сборке, которые возвращают перечислимые типы, такие как массивы.  
  
## <a name="example"></a>Пример  
  
```vb
Imports System.Linq
Imports System.Reflection  

Module Module1  
    Sub Main()  
        Dim asmbly As Assembly =
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()
                            Where type.IsPublic
                            From method In type.GetMethods()
                            Where method.ReturnType.IsArray = True
                            Let name = method.ToString()
                            Let typeName = type.ToString()
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.WriteLine("Press any key to exit... ")  
        Console.ReadKey()  
    End Sub  
End Module  
```  
  
В примере используется метод <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> для возвращения массива типов в указанной сборке. The [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) filter is applied so that only public types are returned. Для каждого открытого типа создается вложенный запрос с использованием массива <xref:System.Reflection.MethodInfo>, который возвращается из вызова <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>. Эти результаты фильтруются для возвращения только тех методов, возвращаемый тип которых является массивом или типом, который реализует <xref:System.Collections.Generic.IEnumerable%601>. Наконец, эти результаты группируются с помощью имени типа в качестве ключа.  
  
## <a name="see-also"></a>См. также

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
