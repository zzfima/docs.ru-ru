---
title: Возможности C#, поддерживающие LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: c617b2d7b56618867fe92cbe1d9ee04aa4c3ab64
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207243"
---
# <a name="c-features-that-support-linq"></a>Возможности C#, поддерживающие LINQ
В следующем разделе приведены новые конструкции языка, представленные в C# 3.0. Несмотря на то, что эти новые возможности в некоторой степени используются с запросами [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], они не ограничиваются [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] и могут использоваться в любом контексте, где они будут целесообразны.  
  
## <a name="query-expressions"></a>Выражения запросов  
 Выражения запросов используют декларативный синтаксис, аналогичный SQL или XQuery, для выполнения запросов к коллекциям IEnumerable. Во время компиляции синтаксис запроса преобразуется в вызовы методов к реализации поставщика [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] методов расширения стандартных операторов запросов. Приложения управляют стандартными операторами запросов в области, указывая соответствующее пространство имен с помощью директивы `using`. Следующее выражение запроса принимает массив строк, группирует их в соответствии с первым символом в строке и упорядочивает группы.  
  
```csharp  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Дополнительные сведения см. в разделе [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## <a name="implicitly-typed-variables-var"></a>Неявно типизированные переменные (var)  
 Вместо явного задания типа при объявлении и инициализации переменной можно использовать модификатор [var](../../../../csharp/language-reference/keywords/var.md), чтобы сообщить компилятору о необходимости определить и присвоить тип, как показано ниже:  
  
```csharp  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Переменные, объявленные как `var`, настолько же строго типизированы, как и переменные, тип которых вы задаете явно. Использование `var` делает возможным создание анонимных типов, однако его можно использовать только для локальных переменных. Массивы также могут быть объявлены путем неявной типизации.  
  
 Дополнительные сведения см. в статье [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Неявно типизированные локальные переменные).  
  
## <a name="object-and-collection-initializers"></a>Инициализаторы объектов и коллекций  
 Инициализаторы объектов и коллекций позволяют инициализировать объекты без явного вызова конструктора для объекта. Инициализаторы обычно используются в выражениях запросов при проецировании исходных данных в новый тип данных. При наличии, например, класса с именем `Customer` с общедоступными свойствами `Name` и `Phone` инициализатор объектов можно использовать как в следующем примере кода:  
  
```csharp  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="anonymous-types"></a>Анонимные типы  
 Анонимный тип создается компилятором, и имя типа доступно только компилятору. Анонимные типы обеспечивают удобный способ временной группировки набора свойств в результатах запроса без необходимости определения отдельного именованного типа. Анонимные типы инициализируются с помощью нового выражения и инициализатора объектов, как показано ниже:  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Дополнительные сведения см. в статье [Анонимные типы](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="extension-methods"></a>Методы расширения  
 Метод расширения представляет собой статический метод, который может быть связан с типом, чтобы его можно было вызывать, как если бы он являлся методом экземпляра типа. Эта возможность позволяет, по сути, "добавлять" новые методы в существующие типы, фактически не изменяя их. Стандартные операторы запросов представляют собой набор методов расширения, предоставляющих функции запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] для любого типа, реализующего интерфейс <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Дополнительные сведения см. в статье [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Лямбда-выражения  
 Лямбда-выражение — это встроенная функция, которая использует оператор => для отделения входных параметров от тела функции и может быть преобразована во время компиляции в делегат или дерево выражения. В программировании [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] вы сталкиваетесь с лямбда-выражениями при выполнении прямых вызовов к стандартным операторам запросов.  
  
 Дополнительные сведения:  
  
-   [Анонимные функции](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Лямбда-выражения](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Деревья выражений (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a>Автоматически реализуемые свойства  
 Свойства, которые реализуются автоматически, упрощают объявление свойств. При объявлении свойства, как показано в следующем примере, компилятор создает закрытое анонимное резервное поле, которое может быть доступно только через методы задания и получения свойства.  
  
```csharp  
public string Name {get; set;}  
```  
  
 Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## <a name="see-also"></a>См. также

- [LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
