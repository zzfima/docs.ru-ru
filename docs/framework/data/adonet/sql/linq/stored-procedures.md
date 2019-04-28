---
title: Хранимые процедуры
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 9201965192f300de62679c1e5be75cf98a24e700
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917947"
---
# <a name="stored-procedures"></a>Хранимые процедуры
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует методы в объектной модели для представления хранимых процедур в базе данных. Чтобы задать методы в качестве хранимых процедур, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute> и, где необходимо, атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>. Дополнительные сведения см. в разделе [LINQ to SQL объектной модели](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Разработчики, использующие Visual Studio обычно используется [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для сопоставления хранимых процедур. В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Возврат наборов строк](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 Содержит сведения о возвращении строк данных и об использовании входного параметра.  
  
 [Практическое руководство. Использование хранимых процедур, принимающих параметры](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 Содержит сведения об использовании входных и выходных параметров.  
  
 [Практическое руководство. Использовать хранимые процедуры, сопоставленные с несколькими результирующими формами](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 Содержит сведения о предоставлении возвратов нескольких фигур в одной хранимой процедуре.  
  
 [Практическое руководство. Использовать хранимые процедуры, сопоставленные с последовательными результирующими формами](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 Содержит сведения о предоставлении нескольких фигур при наличии известной возвращаемой последовательности.  
  
 [Настройка операций за счет хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 Содержит описание использования хранимых процедур для выполнения операций вставки, обновления и удаления.  
  
 [Настройка операций за счет исключительного использования хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 Содержит описание использования только хранимых процедур для выполнения операций вставки, обновления и удаления.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Содержит сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Пошаговое руководство: Применение только хранимых процедур (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 Содержит процедуры, в которых показано использование хранимых процедур в Visual Basic.  
  
 [Пошаговое руководство: Применение только хранимых процедур (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 Содержит процедуры, в которых показано использование хранимых процедур в C#.
