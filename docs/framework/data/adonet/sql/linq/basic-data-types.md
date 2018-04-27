---
title: Базовые типы данных
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e88767bd478b4b59e8c395473cfd8a36aaf68f3b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="basic-data-types"></a>Базовые типы данных
Поскольку запросы LINQ to SQL преобразуются на язык Transact-SQL перед их выполнением на Microsoft SQL Server, LINQ to SQL поддерживает встроенные функции, во многом сходные с теми, которые SQL Server использует для основных типов данных.  
  
## <a name="casting"></a>Приведение  
 Явное или неявное приведение исходных типов CLR к целевым типам CLR возможно, если существует аналогичное допустимое преобразование в рамках SQL Server. Дополнительные сведения о приведении CLR см. в разделе [функция CType](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) и [как](~/docs/csharp/language-reference/keywords/as.md). После преобразования приведение изменяет работу операций, выполняемых над выражением CLR, чтобы они соответствовали поведению других выражений CLR, которые естественным образом сопоставлены с целевым типом. Преобразование приведений типов также возможно в контексте сопоставления наследования. Объекты могут приводиться к более конкретным подтипам сущностей, чтобы обеспечить доступ к данным, характерным для их подтипа.  
  
## <a name="equality-operators"></a>Операторы равенства  
 LINQ to SQL поддерживает следующие операторы равенства для основных типов данных в запросах LINQ to SQL.  
  
-   Оператор равенства и неравенства: операторы равенства и неравенства поддерживаются для числовых типов <xref:System.Boolean>, а также <xref:System.DateTime> и <xref:System.TimeSpan>. Дополнительные сведения о Visual Basic операторы `=` и `<>`, в разделе [операторы сравнения](~/docs/visual-basic/language-reference/operators/comparison-operators.md). Дополнительные сведения об операторах сравнения C# `==` и `!=`, в разделе [==-оператор](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) и [! =-оператор](~/docs/csharp/language-reference/operators/not-equal-operator.md)соответственно  
  
-   Оператор Is: для оператора `IS` имеется поддерживаемый перевод, когда используется сопоставление наследования. Он может использоваться вместо прямой проверки столбца дискриминатора для выяснения, относится ли объект к определенному типу сущности и преобразуется ли он в проверку для столбца дискриминатора. Дополнительные сведения об операторах Visual Basic и C# — см. в разделе [оператор Is](~/docs/visual-basic/language-reference/operators/is-operator.md) и [—](~/docs/csharp/language-reference/keywords/is.md).  
  
## <a name="see-also"></a>См. также  
 [Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
