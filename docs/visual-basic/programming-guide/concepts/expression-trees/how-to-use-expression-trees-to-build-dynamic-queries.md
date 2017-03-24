---
title: "Практическое руководство: использование деревьев выражений для построения динамических запросов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a>Практическое руководство: использование деревьев выражений для построения динамических запросов (Visual Basic)
В LINQ деревья выражений используются для представления источников данных, которые реализуют <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> , целевой структурированных запросов Например, поставщик LINQ реализует <xref:System.Linq.IQueryable%601>интерфейс для выполнения запросов к реляционным хранилищам данных.</xref:System.Linq.IQueryable%601> Компилятор Visual Basic компилирует запросы к источникам данных в код, который строит дерево выражений во время выполнения. Поставщик запросов можно просматривать структуру данных для дерева выражений и преобразовать ее в язык запросов, соответствующий для источника данных.  
  
 Деревья выражений также используются в LINQ для представления лямбда-выражений, которые присваиваются переменным типа <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601>  
  
 В этом разделе описывается использование деревьев выражений для создания динамических запросов LINQ. Динамические запросы полезны в тех случаях, когда характеристики запроса неизвестны во время компиляции. Например приложение может предоставлять пользовательский интерфейс, который позволяет пользователю указать один или несколько предикатов для фильтрации данных. Для использования LINQ для запросов, такой тип приложений должен применять деревья выражений для создания запроса LINQ во время выполнения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование деревьев выражений для создания запроса к `IQueryable` источника данных и затем выполнить его. В коде создается дерево выражения для представления следующего запроса:  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 Фабричные методы в <xref:System.Linq.Expressions>пространства имен используются для создания деревьев выражений, представляющих общий запрос.</xref:System.Linq.Expressions> Выражения, которые представляют вызовы методов стандартных операторов запросов ссылаются <xref:System.Linq.Queryable>реализации этих методов.</xref:System.Linq.Queryable> Итоговое дерево выражения передается <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>реализацию поставщика `IQueryable` источник данных для создания исполняемого запроса типа `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> Результаты получаются путем перечисление переменных запроса.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Этот код использует фиксированное число выражений в предикате, передаваемый `Queryable.Where` метод. Тем не менее можно написать приложение, объединяющее переменное число выражений предиката, зависящее от вводимых пользователем данных. Также можно изменять стандартные операторы, которые вызываются в запросе, в зависимости от входных данных от пользователя.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Создайте новый **консольное приложение** проекта.  
  
-   Добавьте ссылку на System.Core.dll, если нет ссылок.  
  
-   Включите пространство имен System.Linq.Expressions.  
  
-   Скопируйте код из примера и вставьте его в `Main` `Sub` процедуры.  
  
## <a name="see-also"></a>См. также  
 [Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Практическое руководство: выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
