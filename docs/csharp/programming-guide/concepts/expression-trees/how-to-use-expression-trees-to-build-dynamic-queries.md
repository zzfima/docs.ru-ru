---
title: Практическое руководство. Использование деревьев выражений для построения динамических запросов (C#)
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 6114ec13dd43a7df146b87dda00fba06d6eb870c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635903"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a>Практическое руководство. Использование деревьев выражений для построения динамических запросов (C#)
В LINQ деревья выражений используются для представления структурированных запросов к источникам данных, которые реализуют интерфейс <xref:System.Linq.IQueryable%601>. Например, поставщик LINQ реализует интерфейс <xref:System.Linq.IQueryable%601> для выполнения запросов к реляционным хранилищам данных. Компилятор C# компилирует запросы к таким источникам данных в код, который строит дерево выражения во время выполнения. Поставщик запросов может переходить по структуре данных дерева выражения и преобразовать ее в язык запросов, соответствующий источнику данных.  
  
 Деревья выражений также используются в LINQ для представления лямбда-выражений, которые присваиваются переменным типа <xref:System.Linq.Expressions.Expression%601>.  
  
 В этом разделе описывается использование деревьев выражений для создания динамических запросов LINQ. Динамические запросы удобны в тех случаях, когда характеристики запроса неизвестны во время компиляции. Например, приложение может предоставлять пользовательский интерфейс, который позволяет конечному пользователю указать один или несколько предикатов для фильтрации данных. Для использования LINQ для создания запросов такой тип приложения должен использовать деревья выражений для создания запроса LINQ во время выполнения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование деревьев выражений для создания запроса к источнику данных `IQueryable` и его выполнения. В коде создается дерево выражения для представления следующего запроса:  
  
 ```csharp
 companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))
          .OrderBy(company => company)
 ```
  
 Фабричные методы в пространстве имен <xref:System.Linq.Expressions> используются для создания деревьев выражений, представляющих общий запрос. Выражения, которые представляют вызовы методов стандартных операторов запросов, ссылаются на реализации <xref:System.Linq.Queryable> этих методов. Итоговое дерево выражения передается в реализацию <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> поставщика источника данных `IQueryable` для создания исполняемого запроса типа `IQueryable`. Результаты получаются путем перечисления переменной запроса.  
  
```csharp  
// Add a using directive for System.Linq.Expressions.  
  
string[] companies = { "Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",  
                   "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",  
                   "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",  
                   "Blue Yonder Airlines", "Trey Research", "The Phone Company",  
                   "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee" };  
  
// The IQueryable data to query.  
IQueryable<String> queryableData = companies.AsQueryable<string>();  
  
// Compose the expression tree that represents the parameter to the predicate.  
ParameterExpression pe = Expression.Parameter(typeof(string), "company");  
  
// ***** Where(company => (company.ToLower() == "coho winery" || company.Length > 16)) *****  
// Create an expression tree that represents the expression 'company.ToLower() == "coho winery"'.  
Expression left = Expression.Call(pe, typeof(string).GetMethod("ToLower", System.Type.EmptyTypes));  
Expression right = Expression.Constant("coho winery");  
Expression e1 = Expression.Equal(left, right);  
  
// Create an expression tree that represents the expression 'company.Length > 16'.  
left = Expression.Property(pe, typeof(string).GetProperty("Length"));  
right = Expression.Constant(16, typeof(int));  
Expression e2 = Expression.GreaterThan(left, right);  
  
// Combine the expression trees to create an expression tree that represents the  
// expression '(company.ToLower() == "coho winery" || company.Length > 16)'.  
Expression predicateBody = Expression.OrElse(e1, e2);  
  
// Create an expression tree that represents the expression  
// 'queryableData.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))'  
MethodCallExpression whereCallExpression = Expression.Call(  
    typeof(Queryable),  
    "Where",  
    new Type[] { queryableData.ElementType },  
    queryableData.Expression,  
    Expression.Lambda<Func<string, bool>>(predicateBody, new ParameterExpression[] { pe }));  
// ***** End Where *****  
  
// ***** OrderBy(company => company) *****  
// Create an expression tree that represents the expression  
// 'whereCallExpression.OrderBy(company => company)'  
MethodCallExpression orderByCallExpression = Expression.Call(  
    typeof(Queryable),  
    "OrderBy",  
    new Type[] { queryableData.ElementType, queryableData.ElementType },  
    whereCallExpression,  
    Expression.Lambda<Func<string, string>>(pe, new ParameterExpression[] { pe }));  
// ***** End OrderBy *****  
  
// Create an executable query from the expression tree.  
IQueryable<string> results = queryableData.Provider.CreateQuery<string>(orderByCallExpression);  
  
// Enumerate the results.  
foreach (string company in results)  
    Console.WriteLine(company);  
  
/*  This code produces the following output:  
  
    Blue Yonder Airlines  
    City Power & Light  
    Coho Winery  
    Consolidated Messenger  
    Graphic Design Institute  
    Humongous Insurance  
    Lucerne Publishing  
    Northwind Traders  
    The Phone Company  
    Wide World Importers  
*/  
```  
  
 Этот код использует фиксированное число выражений в предикате, передаваемом в метод `Queryable.Where`. Тем не менее можно написать приложение, которое будет сочетать переменное число выражений предиката, зависящих от вводимых пользователем данных. Также можно изменять стандартные операторы запросов, которые вызываются в запросе, в зависимости от входных данных от пользователя.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Включите пространство имен System.Linq.Expressions.  
  
## <a name="see-also"></a>См. также раздел

- [Деревья выражений (C#)](./index.md)
- [Выполнение деревьев выражений (C#)](./how-to-execute-expression-trees.md)
- [Динамическое определение фильтров предикатов во время выполнения](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
