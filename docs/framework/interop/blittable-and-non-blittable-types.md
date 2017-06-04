---
title: "Blittable and Non-Blittable Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interop marshaling, blittable types"
  - "blittable types, interop marshaling"
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Blittable and Non-Blittable Types
Большинство типов данных используют одинаковое представление как в управляемой, так и в неуправляемой памяти, и не требуют специальной обработки упаковщиком взаимодействия.  Такие типы называются *непреобразуемыми типами*, так как они не требуют преобразования при передаче между управляемым и неуправляемым кодом.  
  
 Структуры, возвращаемые из вызовов неуправляемого кода, должны быть непреобразуемыми типами.  Вызов неуправляемого кода не поддерживает преобразуемые структуры как возвращаемые типы.  
  
 Следующие типы из пространства имен <xref:System> являются непреобразуемыми:  
  
-   <xref:System.Byte?displayProperty=fullName>  
  
-   <xref:System.SByte?displayProperty=fullName>  
  
-   <xref:System.Int16?displayProperty=fullName>  
  
-   <xref:System.UInt16?displayProperty=fullName>  
  
-   <xref:System.Int32?displayProperty=fullName>  
  
-   <xref:System.UInt32?displayProperty=fullName>  
  
-   <xref:System.Int64?displayProperty=fullName>  
  
-   <xref:System.UInt64?displayProperty=fullName>  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Single?displayProperty=fullName>  
  
-   <xref:System.Double?displayProperty=fullName>  
  
 Непреобразуемыми также являются следующие сложные типы:  
  
-   Одномерные массивы непреобразуемых типов, такие как массивы целых чисел.  Но тип, содержащий переменный массив непреобразуемых типов уже не является преобразуемым.  
  
-   Форматированные типы значений, содержащие только непреобразуемые типы \(и классы, если они маршалируются как форматированные типы\)  Дополнительные сведения о передаче форматированных типов значений см. в разделе [Default Marshaling for Value Types](http://msdn.microsoft.com/ru-ru/4d9a876c-e05a-40ba-bd85-bd22877f984a).  
  
 Ссылки на объекты не являются непреобразуемыми.  Это распространяется и на массив ссылок на объекты, которые сами по себе являются непреобразуемыми.  Например, можно определить структуру, являющуюся непреобразуемым, но нельзя определить непреобразуемый тип, содержащий массив ссылок на эти структуры.  
  
 Для оптимизации массивы непреобразуемых типов и классы, содержащие только непреобразуемые члены, при маршалинге не копируются, а [закрепляются](../../../docs/framework/interop/copying-and-pinning.md).  Когда вызывающий и вызываемый объекты находятся в одном подразделении, маршалинг таких типов выглядит как маршалинг с параметрами In\/Out.  Но в действительности маршалинг этих типов выполняется как маршалинг параметров In, и разработчик должен использовать атрибуты <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, если ему нужно выполнить маршалинг аргумента как параметра In\/Out.  
  
 Некоторые управляемые типы данных требуют отличающегося представления в неуправляемой среде.  Эти преобразуемые типы данных должны быть преобразованы к виду, для которого может быть выполнен маршалинг.  Например, управляемые строки являются преобразуемыми типами, так как они должны быть преобразованы в строковые объекты, прежде чем может быть выполнен их маршалинг.  
  
 В следующей таблице перечислены преобразуемые типы из пространства имен <xref:System>.  [Делегаты](http://msdn.microsoft.com/ru-ru/d176ee76-f982-494b-b03d-92e4118896e2), являющиеся структурами данных, ссылающимися на статический метод или к экземпляр класса, также являются преобразуемыми.  
  
|Преобразуемый тип|Описание|  
|-----------------------|--------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Преобразуется в массив в стиле языка C или в `SAFEARRAY`.|  
|[System.Boolean](http://msdn.microsoft.com/ru-ru/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|Преобразуется в значение размерностью 1, 2, или 4 байта, равное 1 или –1 в случае значения `true`.|  
|[System.Char](http://msdn.microsoft.com/ru-ru/cecc87c1-075e-4cde-aa56-33d189f66feb)|Преобразуется в знак в кодировке Юникод или ANSI.|  
|[System.Class](http://msdn.microsoft.com/ru-ru/fe334af5-0123-43d8-be84-26f6f023ddb6)|Преобразуется в интерфейс класса.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Преобразуется в тип Variant или интерфейс.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Преобразуется в массив в стиле языка C или в `SAFEARRAY`.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Преобразуется в строку, завершающуюся пустой ссылкой или BSTR.|  
|[System.Valuetype](http://msdn.microsoft.com/ru-ru/4d9a876c-e05a-40ba-bd85-bd22877f984a)|Преобразуется в структуру с фиксированным расположением в памяти.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Преобразуется в массив в стиле языка C или в `SAFEARRAY`.|  
  
 Типы классов и объектов поддерживаются только COM\-взаимодействием.  Соответствующие типы в [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# и C\+\+ см. в разделе [Общие сведения о библиотеке классов](../../../docs/standard/class-library-overview.md).  
  
## См. также  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)