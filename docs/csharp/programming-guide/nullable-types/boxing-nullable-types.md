---
title: "Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "упаковка-преобразование [C#], типы, допускающие значения NULL"
  - "типы, допускающие значения NULL [C#], упаковка-преобразование и распаковка-преобразование"
  - "распаковка-преобразование [C#], типы, допускающие значения NULL"
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)
Объекты на основе типов, допускающих значения NULL, могут быть упакованы, только если объект имеет значение, отличное от NULL.   Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, ссылке на объект присваивается `null` и упаковка не выполняется.  Примеры.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Объект имеет значение, отличное от NULL: если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`, выполняется упаковка, однако упаковывается только базовый тип, который лежит в основе объекта, допускающего значения NULL.  При упаковке ненулевого типа значения, допускающего NULL, происходит упаковка самого типа значения, а не <xref:System.Nullable%601?displayProperty=fullName>, который упаковывает тип значения.  Примеры.  
  
```  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Два упакованных объекта идентичны объектам, созданным при упаковке типов со значениями, отличными от NULL.  И так же как и упакованные типы со значениями, отличными от NULL, они могут быть распакованы в типы, допускающие значения NULL, как показано в следующем примере.  
  
```  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## Заметки  
 Поведение упакованных типов, допускающих значения NULL, предоставляет два преимущества.  
  
1.  Объекты, допускающие значения NULL, и их упакованные аналоги можно проверить на наличие значения NULL.  
  
    ```  
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
  
2.  Упакованные типы, допускающие значения NULL, полностью поддерживают функциональность базового типа.  
  
    ```  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Практическое руководство. Идентификация типа, допускающего значение NULL](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)