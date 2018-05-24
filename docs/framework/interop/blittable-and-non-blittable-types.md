---
title: Преобразуемые и непреобразуемые типы
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acef752cf54d28dd1f07431b5dbbadbac0b7849e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="blittable-and-non-blittable-types"></a>Преобразуемые и непреобразуемые типы
Большинство типов данных имеют общее представление как в управляемой, так и в неуправляемой памяти и не требуют специальной обработки со стороны маршалера взаимодействия. Такие типы называются *непреобразуемыми*, поскольку при их передаче между управляемым и неуправляемым кодом не требуется преобразование.  
  
 Структуры, возвращаемые из вызовов неуправляемого кода, должны иметь непреобразуемый тип. Вызовы неуправляемого кода не поддерживают преобразуемые структуры, такие как типы возвращаемых значений.  
  
 Следующие типы из пространства имен <xref:System> относятся к непреобразуемым:  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 Также непреобразуемыми являются следующие сложные типы:  
  
-   Одномерные массивы непреобразуемых типов, например массивы целых чисел. Тем не менее тип, содержащий переменный массив непреобразуемых типов, сам по себе не является непреобразуемым.  
  
-   Форматированные типы значений, содержащие только непреобразуемые типы (и классы, если они маршалируются как непреобразуемые типы). Дополнительные сведения о форматированных типах значений см. в разделе [Маршалинг по умолчанию для типов значений](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100)).  
  
 Ссылки на объекты не относятся к непреобразуемым типам. Это справедливо для массивов ссылок на объекты, которые сами по себе являются непреобразуемыми. Например, можно определить непреобразуемую структуру, однако при этом нельзя определить непреобразуемый тип, который содержит массив ссылок на такие структуры.  
  
 В целях оптимизации массивы непреобразуемых типов и классов, которые содержат только непреобразуемые члены, при маршалинге [закрепляются](../../../docs/framework/interop/copying-and-pinning.md), а не копируются. Эти типы могут маршалироваться как параметры ввода-вывода, если вызывающий и вызываемый объект находятся в одном подразделении. Тем не менее такие типы фактически маршалируются как параметры ввода. Чтобы маршалировать аргумент как параметр ввода-вывода, необходимо применить атрибуты <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>.  
  
 Некоторые управляемые типы данных требуют отличающегося представления в неуправляемой среде. Такие преобразуемые типы данных должны преобразовываться в форму, подходящую для маршалинга. Например, управляемые строки относятся к преобразуемым типам, поскольку перед выполнением маршалинга их необходимо преобразовывать в строковые объекты.  
  
 В следующей таблице перечислены преобразуемые типы из пространства имен <xref:System>. [Делегаты](https://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2(v=vs.100)), представляющие собой структуры данных, которые ссылаются на статический метод или экземпляр класса, также являются преобразуемыми.  
  
|Преобразуемые типы|Описание:|  
|-------------------------|-----------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Преобразует в массив в стиле C или `SAFEARRAY`.|  
|[System.Boolean](https://msdn.microsoft.com/library/d4c00537-70f7-4ca6-8197-bfc1ec037ff9(v=vs.100))|Преобразует в одно-, двух- или четырехбайтовое значение, где `true` выражается как 1 или -1.|  
|[System.Char](https://msdn.microsoft.com/library/cecc87c1-075e-4cde-aa56-33d189f66feb(v=vs.100))|Преобразует в символ Юникода или ANSI.|  
|[System.Class](https://msdn.microsoft.com/library/fe334af5-0123-43d8-be84-26f6f023ddb6(v=vs.100))|Преобразует в интерфейс класса.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Преобразует в вариант или интерфейс.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Преобразует в массив в стиле C или `SAFEARRAY`.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Преобразует в строку, завершающуюся ссылкой NULL, или в BSTR.|  
|[System.Valuetype](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100))|Преобразует в структуру с фиксированным расположением в памяти.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Преобразует в массив в стиле C или `SAFEARRAY`.|  
  
 Типы классов и объектов поддерживаются только COM-взаимодействием. Информацию о соответствующих типах в [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# и C++ см. в разделе [Обзор библиотеки классов](../../../docs/standard/class-library-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Характеристики маршалинга по умолчанию](../../../docs/framework/interop/default-marshaling-behavior.md)
