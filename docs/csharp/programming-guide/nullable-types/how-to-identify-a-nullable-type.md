---
title: "Практическое руководство. Идентификация типа, допускающего значение NULL (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "типы, допускающие значения NULL [C#], выявление"
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Идентификация типа, допускающего значение NULL (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор C\# [typeof](../../../csharp/language-reference/keywords/typeof.md) может использоваться для создания объекта <xref:System.Type>, представляющего обнуляемый тип:  
  
```  
System.Type type = typeof(int?);  
```  
  
 Также можно использовать классы и методы пространства имен <xref:System.Reflection> для создания объектов <xref:System.Type>, представляющих обнуляемые типы.  Однако при попытке получить информацию о типе от обнуляемых переменных во время выполнения, используя метод <xref:System.Object.GetType%2A> или оператор `is`, результатом является объект <xref:System.Type>, представляющий базовый тип, а не сам обнуляемый тип.  
  
 Вызов `GetType` для обнуляемого типа приводит к выполнению операции упаковки\-преобразования в момент неявного преобразования типа в <xref:System.Object>.  Таким образом, <xref:System.Object.GetType%2A> всегда возвращает объект <xref:System.Type>, представляющий базовый тип, а не обнуляемый тип.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 Оператор C\# [is](../../../csharp/language-reference/keywords/is.md) также работает с базовым типом для обнуляемого типа.  Поэтому нельзя использовать `is` для определения, является ли тип переменной обнуляемым.  В следующем примере показано, что оператор `is` рассматривает обнуляемую переменную\<int\> просто как "int".  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## Пример  
 Чтобы определить, представляет ли объект <xref:System.Type> обнуляемый тип, используйте следующий код.  Помните, что код всегда возвращает значение "false", если объект `Type` был возвращен из вызова <xref:System.Object.GetType%2A>, как описано ранее в этом разделе.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## См. также  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Упаковка\-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)