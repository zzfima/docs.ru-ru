---
title: Базовые типы данных
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: e85adb928925bf161e6e2d6ef935a20606f8eb32
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248028"
---
# <a name="basic-data-types"></a>Базовые типы данных
Поскольку запросы LINQ to SQL преобразуются на язык Transact-SQL перед их выполнением на Microsoft SQL Server, LINQ to SQL поддерживает встроенные функции, во многом сходные с теми, которые SQL Server использует для основных типов данных.  
  
## <a name="casting"></a>Приведение  
 Явное или неявное приведение исходных типов CLR к целевым типам CLR возможно, если существует аналогичное допустимое преобразование в рамках SQL Server. Дополнительные сведения о приведении среды CLR см. в разделе [функции CType](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) и [операторы проверки и приведения типов](../../../../../csharp/language-reference/operators/type-testing-and-cast.md). После преобразования приведение изменяет работу операций, выполняемых над выражением CLR, чтобы они соответствовали поведению других выражений CLR, которые естественным образом сопоставлены с целевым типом. Преобразование приведений типов также возможно в контексте сопоставления наследования. Объекты могут приводиться к более конкретным подтипам сущностей, чтобы обеспечить доступ к данным, характерным для их подтипа.  
  
## <a name="equality-operators"></a>Операторы равенства  
 LINQ to SQL поддерживает следующие операторы равенства для основных типов данных в запросах LINQ to SQL.  
  
- Оператор «меньше или равно»: Операторы равенства и неравенства поддерживаются для числовых типов, <xref:System.Boolean>, <xref:System.DateTime>и <xref:System.TimeSpan> . Дополнительные сведения об операторах `=` Visual Basic `<>`и см. в разделе [Операторы сравнения](../../../../../visual-basic/language-reference/operators/comparison-operators.md). C# Дополнительные сведения об операторах `==` сравнения и `!=`см. в разделе [Операторы равенства](../../../../../csharp/language-reference/operators/equality-operators.md).
  
- Оператор IS: для оператора `IS` имеется поддерживаемый перевод, когда используется сопоставление наследования. Он может использоваться вместо прямой проверки столбца дискриминатора для выяснения, относится ли объект к определенному типу сущности и преобразуется ли он в проверку для столбца дискриминатора. Дополнительные сведения об операторах Visual Basic и C# is см. в описании [оператора is](../../../../../visual-basic/language-reference/operators/is-operator.md) и [is](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>См. также

- [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md)
- [Типы данных и функции](data-types-and-functions.md)
