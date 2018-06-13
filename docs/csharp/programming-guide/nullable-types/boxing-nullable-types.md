---
title: Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
ms.openlocfilehash: e2c7602bf45f1861d3a32a73824e9fedf0a4d29d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334760"
---
# <a name="boxing-nullable-types-c-programming-guide"></a>Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)
Объекты на основе типов, допускающих значения NULL, могут быть упакованы, только если объект имеет значение, отличное от NULL. Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, ссылке на объект присваивается `null` и упаковка-преобразование не выполняется. Пример:  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 Объект имеет значение, отличное от NULL, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`, выполняется упаковка-преобразование, однако упаковывается только базовый тип, который лежит в основе объекта, допускающего значение NULL. При упаковке-преобразовании ненулевого типа значения, допускающего NULL, происходит упаковка самого типа значения, а не <xref:System.Nullable%601?displayProperty=nameWithType>, который упаковывает тип значения. Пример:  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Два упакованных объекта идентичны объектам, созданным при упаковке-преобразовании типов со значениями, отличными от NULL. И так же, как и упакованные типы со значениями, отличными от NULL, они могут быть распакованы в типы, допускающие значения NULL, как показано в следующем примере:  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>Примечания  
 Поведение упакованных типов, допускающих значения NULL, предоставляет два преимущества:  
  
1.  Объекты, допускающие значения NULL и их упакованные аналоги, можно проверить на наличие значения NULL:  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  Упакованные типы, допускающие значения NULL, полностью поддерживают функциональность базового типа:  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
 [Практическое руководство. Идентификация типа, допускающего значение NULL](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
