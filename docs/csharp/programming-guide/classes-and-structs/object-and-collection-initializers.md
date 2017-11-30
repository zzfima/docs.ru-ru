---
title: "Инициализаторы объектов и коллекций (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7445a2919baaa477b4611c4c5ee5a0031539ca30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Инициализаторы объектов и коллекций (Руководство по программированию в C#)
Инициализаторы объектов позволяют присваивать значения всем доступным полям и свойствам объекта во время создания без вызова конструктора, за которым следуют строки операторов присваивания. Синтаксис инициализатора объекта позволяет задавать аргументы конструктора или опускать их (и синтаксис в скобках).  В следующем примере показаны использование инициализатора объекта с именованным типом `Cat` и вызов конструктора по умолчанию. Обратите внимание на использование в классе `Cat` автоматически внедренных свойств. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
Синтаксис инициализаторы объектов можно создать экземпляр, а после этого вновь созданный объект со свойствами, назначенный, присваивает переменной в назначении.
  
## <a name="object-initializers-with-anonymous-types"></a>Инициализаторы объектов с анонимными типами  
 Хотя инициализаторы объектов можно использовать в любом контексте, они особенно полезны в выражениях запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. В выражениях запросов часто используются [анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), которые можно инициализировать только с помощью инициализаторов объектов, как показано в приведенном ниже объявлении.  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Анонимные типы позволяют предложению `select` в выражении запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] преобразовывать объекты исходной последовательности в объекты, значение и форма которых могут отличаться от исходных. Это бывает полезно, если требуется сохранить лишь часть информации от каждого объекта последовательности. В приведенном ниже примере предполагается, что у объекта продукта (`p`) имеется множество полей и методов, и требуется создать последовательность объектов, содержащую только имя продукта и его цену.  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 При выполнении этого запроса переменная `productInfos` будет содержать последовательность объектов, доступных в операторе `foreach`, как показано в следующем примере.  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 Каждый объект нового анонимного типа содержит два общедоступных свойства, имеющих те же имена, что и у свойств или полей исходного объекта. Кроме того, при создании анонимного типа можно переименовать поле; в следующем примере выполняется переименование поля `UnitPrice` в `Price`.  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a>Инициализаторы объектов с типами, допускающими значение NULL  
 При попытке использовать инициализатор объекта со структурой, допускающей значение NULL, произойдет ошибка компиляции.  
  
## <a name="collection-initializers"></a>Инициализаторы коллекций  
 Инициализаторы коллекций позволяют задавать один или несколько инициализаторов элементов при инициализации типа коллекции, который реализует интерфейс <xref:System.Collections.IEnumerable> и включает `Add` с соответствующей сигнатурой как метод экземпляра или метод расширения. Инициализаторами элементов могут быть простые значения, выражения и инициализаторы объектов. При использовании инициализатора коллекции не требуется указывать в исходном коде несколько вызовов метода `Add` класса; эти вызовы добавляет компилятор.  
  
 Ниже приведены два примера простых инициализаторов коллекций.  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 В следующем инициализаторе коллекции используются инициализаторы объектов класса `Cat`, определенного в предыдущем примере. Обратите внимание, что инициализаторы отдельных объектов заключены в скобки и разделены запятыми.  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 В качестве элемента инициализатора коллекции можно указать значение [null](../../../csharp/language-reference/keywords/null.md), если метод `Add` коллекции допускает это.  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Можно указать индексированные элементы, если коллекция поддерживает индексирование.  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
