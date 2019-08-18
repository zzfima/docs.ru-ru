---
title: Базовые типы данных
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: 249155e185986504a85451c367c5b41cc5e68d96
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567394"
---
# <a name="basic-data-types"></a>Базовые типы данных
Поскольку запросы LINQ to SQL преобразуются на язык Transact-SQL перед их выполнением на Microsoft SQL Server, LINQ to SQL поддерживает встроенные функции, во многом сходные с теми, которые SQL Server использует для основных типов данных.  
  
## <a name="casting"></a>Приведение  
 Явное или неявное приведение исходных типов CLR к целевым типам CLR возможно, если существует аналогичное допустимое преобразование в рамках SQL Server. Дополнительные сведения о приведении среды CLR см. в разделе [функции CType](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) и [операторы проверки и приведения типов](~/docs/csharp/language-reference/operators/type-testing-and-cast.md). После преобразования приведение изменяет работу операций, выполняемых над выражением CLR, чтобы они соответствовали поведению других выражений CLR, которые естественным образом сопоставлены с целевым типом. Преобразование приведений типов также возможно в контексте сопоставления наследования. Объекты могут приводиться к более конкретным подтипам сущностей, чтобы обеспечить доступ к данным, характерным для их подтипа.  
  
## <a name="equality-operators"></a>Операторы равенства  
 LINQ to SQL поддерживает следующие операторы равенства для основных типов данных в запросах LINQ to SQL.  
  
- Оператор «меньше или равно»: Операторы равенства и неравенства поддерживаются для числовых типов, <xref:System.Boolean>, <xref:System.DateTime>и <xref:System.TimeSpan> . Дополнительные сведения об операторах `=` Visual Basic `<>`и см. в разделе [Операторы сравнения](~/docs/visual-basic/language-reference/operators/comparison-operators.md). C# Дополнительные сведения об операторах `==` сравнения и `!=`см. в разделе [Операторы равенства](~/docs/csharp/language-reference/operators/equality-operators.md).
  
- Оператор IS: для оператора `IS` имеется поддерживаемый перевод, когда используется сопоставление наследования. Он может использоваться вместо прямой проверки столбца дискриминатора для выяснения, относится ли объект к определенному типу сущности и преобразуется ли он в проверку для столбца дискриминатора. Дополнительные сведения об операторах Visual Basic и C# is см. в описании [оператора is](~/docs/visual-basic/language-reference/operators/is-operator.md) и [is](~/docs/csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>См. также

- [Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
