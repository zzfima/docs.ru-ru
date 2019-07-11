---
title: Пользовательские функции
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 54faca27e3f70283144f902e531e2a08e45bae3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742713"
---
# <a name="user-defined-functions"></a>Пользовательские функции
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует методы в объектной модели для представления пользовательских функций. Чтобы назначить методы в качестве функций, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>, а где необходимо - атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>. Дополнительные сведения см. в разделе [LINQ to SQL объектной модели](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Чтобы избежать <xref:System.InvalidOperationException>, пользовательские функции в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] должны быть представлены в одной из следующих форм.  
  
- Функция, упакованная в качестве вызова метода с правильными атрибутами сопоставления. Дополнительные сведения см. в разделе [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
- Статический метод SQL, характерный для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
- Функция, поддерживаемая методом .NET Framework.  
  
 В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода. Разработчики, использующие Visual Studio обычно используется для сопоставления определяемых пользователем функций реляционного конструктора объектов.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Используйте скалярные определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 Описано, как реализовать функцию, возвращающую скалярные значения.  
  
 [Практическое руководство. Использование возвращающих табличные значения определяемых пользователем функций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 Содержит описание способов реализации функции, возвращающей табличные значения.  
  
 [Практическое руководство. Вызывать встроенные определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 Содержит описание преобразования встроенных вызовов в функции и представляет различия при внутреннем осуществлении вызова.
