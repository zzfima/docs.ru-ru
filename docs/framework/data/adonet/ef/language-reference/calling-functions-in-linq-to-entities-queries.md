---
title: Вызов функций в запросах LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251267"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Вызов функций в запросах LINQ to Entities
В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.  
  
 Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework. Дополнительные сведения см. в разделе [Практическое руководство. Вызывайте канонические [функции](how-to-call-canonical-functions.md) и как: Вызывайте функции](how-to-call-database-functions.md)базы данных.  
  
 Процесс вызова пользовательской функции состоит из трех основных шагов.  
  
1. Определите функцию в концептуальной модели или объявите функцию в модели хранения.  
  
2. Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3. Вызовите функцию в запросе LINQ to Entities.  
  
 Дополнительные сведения см. в подразделах этого раздела.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Вызов канонических функций](how-to-call-canonical-functions.md)  
  
 [Практическое руководство. Вызов функций базы данных](how-to-call-database-functions.md)  
  
 [Практическое руководство. Вызов пользовательских функций базы данных](how-to-call-custom-database-functions.md)  
  
 [Практическое руководство. Вызов определяемых моделью функций в запросах](how-to-call-model-defined-functions-in-queries.md)  
  
 [Практическое руководство. Вызов определяемых моделью функций в качестве методов объекта](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>См. также

- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
- [Канонические функции](canonical-functions.md)
- [Общие сведения о файле EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Практическое руководство. Определение пользовательских функций в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
