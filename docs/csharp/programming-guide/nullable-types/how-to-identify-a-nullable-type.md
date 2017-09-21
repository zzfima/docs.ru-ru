---
title: "Практическое руководство. Идентификация типа, допускающего значение NULL (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c9e05bfe8be45e5b71a8db06ce4f2502c5397fd4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Практическое руководство. Идентификация типа, допускающего значение NULL (Руководство по программированию на C#)
С помощью оператора C# [typeof](../../../csharp/language-reference/keywords/typeof.md) можно создать объект <xref:System.Type>, который представляет тип, допускающий значения NULL:  
  
```  
System.Type type = typeof(int?);  
```  
  
 Кроме того, можно использовать классы и методы из пространства имен <xref:System.Reflection> для создания объектов <xref:System.Type>, которые представляют типы, допускающие значения NULL. Тем не менее при попытке получить во время выполнения сведения о типе для переменных, допускающих значения NULL, используя метод <xref:System.Object.GetType%2A> оператора `is`, возвращается объект <xref:System.Type>, который представляет базовый тип, а не сам тип, допускающий значения NULL.  
  
 При вызове метода `GetType` для типа, допускающего значения NULL, выполняется операция упаковки-преобразования при неявном преобразовании типа в <xref:System.Object>. Таким образом, метод <xref:System.Object.GetType%2A> всегда возвращает объект <xref:System.Type>, который представляет базовый тип, а не сам тип, допускающий значения NULL.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 Оператор C# [is](../../../csharp/language-reference/keywords/is.md) также работает с базовым типом для типа, допускающего значения NULL. Поэтому нельзя использовать оператор `is`, чтобы определить, имеет ли переменная тип, допускающий значения NULL. В следующем примере показано, что оператор `is` рассматривает переменную \<int>, допускающую значения NULL, как переменную int.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий код позволяет определить, представляет ли объект <xref:System.Type> тип, допускающий значения NULL. Обратите внимание, что этот код всегда возвращает значение false, если объект `Type` был возвращен из вызова <xref:System.Object.GetType%2A>, как описывается выше в этом разделе.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a>См. также  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Упаковка-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)

