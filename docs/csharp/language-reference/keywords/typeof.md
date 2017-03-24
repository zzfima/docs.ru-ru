---
title: "typeof (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "typeof"
  - "typeof_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "typeof - ключевое слово [C#]"
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# typeof (справочник по C#)
Используется для получения объекта `System.Type` для типа.  Выражение `typeof` принимает следующую форму:  
  
```  
System.Type type = typeof(int);  
```  
  
## Заметки  
 Для получения типа выражения во время выполнения можно воспользоваться методом платформы .NET <xref:System.Object.GetType%2A>, как показано в следующем примере:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Оператор `typeof` перегрузить нельзя.  
  
 Оператор `typeof` может также использоваться с открытыми универсальными типами.  Типы с более чем одним параметром типа должны иметь соответствующее количество запятых в спецификации.  В следующем примере показано, как определить, является ли тип возвращаемого значения универсальным <xref:System.Collections.Generic.IEnumerable%601>.  Предполагается, что метод является экземпляром типа MethodInfo:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## Пример  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## Пример  
 В этом примере для определения типа, используемого для размещения результата численного вычисления, применен метод <xref:System.Object.GetType%2A>.  Тип зависит от требований, предъявляемых для хранения получаемого в результате числа.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Type?displayProperty=fullName>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)