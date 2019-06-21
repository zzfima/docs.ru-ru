---
title: Базовые типы данных
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: 6e1e48b3d390cf7c8ec81735b9637f706ad3a0ad
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306265"
---
# <a name="basic-data-types"></a>Базовые типы данных
Поскольку запросы LINQ to SQL преобразуются на язык Transact-SQL перед их выполнением на Microsoft SQL Server, LINQ to SQL поддерживает встроенные функции, во многом сходные с теми, которые SQL Server использует для основных типов данных.  
  
## <a name="casting"></a>Приведение  
 Явное или неявное приведение исходных типов CLR к целевым типам CLR возможно, если существует аналогичное допустимое преобразование в рамках SQL Server. Дополнительные сведения о приведении CLR см. в разделе [функция CType](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) и [операторы тестирования типа и преобразования](~/docs/csharp/language-reference/operators/type-testing-and-conversion-operators.md). После преобразования приведение изменяет работу операций, выполняемых над выражением CLR, чтобы они соответствовали поведению других выражений CLR, которые естественным образом сопоставлены с целевым типом. Преобразование приведений типов также возможно в контексте сопоставления наследования. Объекты могут приводиться к более конкретным подтипам сущностей, чтобы обеспечить доступ к данным, характерным для их подтипа.  
  
## <a name="equality-operators"></a>Операторы равенства  
 LINQ to SQL поддерживает следующие операторы равенства для основных типов данных в запросах LINQ to SQL.  
  
- Оператор «меньше или равно»: Операторы равенства и неравенства поддерживаются для числовых, <xref:System.Boolean>, <xref:System.DateTime>, и <xref:System.TimeSpan> типы. Дополнительные сведения об операторах Visual Basic `=` и `<>`, см. в разделе [операторы сравнения](~/docs/visual-basic/language-reference/operators/comparison-operators.md). Дополнительные сведения о C# операторы сравнения `==` и `!=`, см. в разделе [операторы равенства](~/docs/csharp/language-reference/operators/equality-operators.md).
  
- Оператор IS: для оператора `IS` имеется поддерживаемый перевод, когда используется сопоставление наследования. Он может использоваться вместо прямой проверки столбца дискриминатора для выяснения, относится ли объект к определенному типу сущности и преобразуется ли он в проверку для столбца дискриминатора. Дополнительные сведения о Visual Basic и C# имеет значение operators, см. в разделе [оператор Is](~/docs/visual-basic/language-reference/operators/is-operator.md) и [—](~/docs/csharp/language-reference/operators/type-testing-and-conversion-operators.md#is-operator).  
  
## <a name="see-also"></a>См. также

- [Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
