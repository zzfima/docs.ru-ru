---
title: Преобразуемые и непреобразуемые типы
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 816b854120f09efef69bd8ceb2d3650e5a8e7af0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123737"
---
# <a name="blittable-and-non-blittable-types"></a>Преобразуемые и непреобразуемые типы
Большинство типов данных имеют общее представление как в управляемой, так и в неуправляемой памяти и не требуют специальной обработки со стороны маршалера взаимодействия. Такие типы называются *непреобразуемыми*, поскольку при их передаче между управляемым и неуправляемым кодом не требуется преобразование.  
  
 Структуры, возвращаемые из вызовов неуправляемого кода, должны иметь непреобразуемый тип. Вызовы неуправляемого кода не поддерживают преобразуемые структуры, такие как типы возвращаемых значений.  
  
 Следующие типы из пространства имен <xref:System> относятся к непреобразуемым:  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 Также непреобразуемыми являются следующие сложные типы:  
  
- Одномерные массивы непреобразуемых типов, например массивы целых чисел. Тем не менее тип, содержащий переменный массив непреобразуемых типов, сам по себе не является непреобразуемым.  
  
- Форматированные типы значений, содержащие только непреобразуемые типы (и классы, если они маршалируются как непреобразуемые типы). Дополнительные сведения о форматированных типах значений см. в разделе [Маршалинг по умолчанию для типов значений](default-marshaling-behavior.md#default-marshaling-for-value-types).  
  
 Ссылки на объекты не относятся к непреобразуемым типам. Это справедливо для массивов ссылок на объекты, которые сами по себе являются непреобразуемыми. Например, можно определить непреобразуемую структуру, однако при этом нельзя определить непреобразуемый тип, который содержит массив ссылок на такие структуры.  
  
 В целях оптимизации массивы непреобразуемых типов и классов, которые содержат только непреобразуемые члены, при маршалинге [закрепляются](copying-and-pinning.md), а не копируются. Эти типы могут маршалироваться как параметры ввода-вывода, если вызывающий и вызываемый объект находятся в одном подразделении. Тем не менее такие типы фактически маршалируются как параметры ввода. Чтобы маршалировать аргумент как параметр ввода-вывода, необходимо применить атрибуты <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>.  
  
 Некоторые управляемые типы данных требуют отличающегося представления в неуправляемой среде. Такие преобразуемые типы данных должны преобразовываться в форму, подходящую для маршалинга. Например, управляемые строки относятся к преобразуемым типам, поскольку перед выполнением маршалинга их необходимо преобразовывать в строковые объекты.  
  
 В следующей таблице перечислены преобразуемые типы из пространства имен <xref:System>. [Делегаты](default-marshaling-behavior.md#default-marshaling-for-delegates), представляющие собой структуры данных, которые ссылаются на статический метод или экземпляр класса, также являются преобразуемыми.  
  
|Преобразуемые типы|Описание|  
|-------------------------|-----------------|  
|[System.Array](default-marshaling-for-arrays.md)|Преобразует в массив в стиле C или `SAFEARRAY`.|  
|[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))|Преобразует в одно-, двух- или четырехбайтовое значение, где `true` выражается как 1 или -1.|  
|[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))|Преобразует в символ Юникода или ANSI.|  
|[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))|Преобразует в интерфейс класса.|  
|[System.Object](default-marshaling-for-objects.md)|Преобразует в вариант или интерфейс.|  
|[System.Mdarray](default-marshaling-for-arrays.md)|Преобразует в массив в стиле C или `SAFEARRAY`.|  
|[System.String](default-marshaling-for-strings.md)|Преобразует в строку, завершающуюся ссылкой NULL, или в BSTR.|  
|[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))|Преобразует в структуру с фиксированным расположением в памяти.|  
|[System.Szarray](default-marshaling-for-arrays.md)|Преобразует в массив в стиле C или `SAFEARRAY`.|  
  
 Типы классов и объектов поддерживаются только COM-взаимодействием. Для соответствующих типов в Visual Basic, C# и C++ см. раздел [Обзор библиотеки классов](../../standard/class-library-overview.md).  
  
## <a name="see-also"></a>См. также

- [Характеристики маршалинга по умолчанию](default-marshaling-behavior.md)
