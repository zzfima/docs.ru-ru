---
title: Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: 65f27ae17d77553bfd7a78c1310febd337a55a6e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345687"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a>Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)

API отражения библиотеки классов .NET Framework можно использовать для просмотра метаданных в сборке .NET и создания коллекций типов, членов типов, параметров и т. д., присутствующих в этой сборке. Поскольку эти коллекции поддерживают универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, их можно запрашивать с помощью LINQ.  
  
В следующем примере показано использование LINQ с отражением для извлечения определенных метаданных о методах, соответствующих условиям поиска. В этом примере запрос будет искать имена всех методов в сборке, которые возвращают перечислимые типы, такие как массивы.  
  
## <a name="example"></a>Пример  
  
```csharp  
using System;
using System.Linq;
using System.Reflection;  

class ReflectionHowTO  
{  
    static void Main()  
    {  
        Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
        var pubTypesQuery = from type in assembly.GetTypes()  
                    where type.IsPublic  
                        from method in type.GetMethods()  
                        where method.ReturnType.IsArray == true 
                            || ( method.ReturnType.GetInterface(  
                                typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                            && method.ReturnType.FullName != "System.String" )  
                        group method.ToString() by type.ToString();  

        foreach (var groupOfMethods in pubTypesQuery)  
        {  
            Console.WriteLine("Type: {0}", groupOfMethods.Key);  
            foreach (var method in groupOfMethods)  
            {  
                Console.WriteLine("  {0}", method);  
            }  
        }  

        Console.WriteLine("Press any key to exit... ");  
        Console.ReadKey();  
    }  
}
```  

В примере используется метод <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> для возвращения массива типов в указанной сборке. Чтобы вернуть только открытые типы, применяется фильтр [where](../../../language-reference/keywords/where-clause.md). Для каждого открытого типа создается вложенный запрос с использованием массива <xref:System.Reflection.MethodInfo>, который возвращается из вызова <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>. Эти результаты фильтруются для возвращения только тех методов, возвращаемый тип которых является массивом или типом, который реализует <xref:System.Collections.Generic.IEnumerable%601>. Наконец, эти результаты группируются с помощью имени типа в качестве ключа.  
  
## <a name="see-also"></a>См. также

- [LINQ to Objects (C#)](./linq-to-objects.md)
