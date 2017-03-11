---
title: "Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc33107"
  - "vbc33107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33107"
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Выражение `If` может принимать два или три аргумента.  При передаче двух аргументов, первый аргумент должен быть ссылочного типа или поддерживать значение NULL.  Если первый аргумент принимает значение, отличное от `Nothing`, возвращается его значение.  Если первый аргумент принимает значение `Nothing`, то вычисляется и возвращается значение второго аргумента.  
  
 Например, следующий код содержит два выражения `If`, одно с тремя аргументами и другое с двумя.  Выражения вычисляют и возвращают одно и то же значение.  
  
```vb#  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Следующие выражения вызывают эту ошибку.  
  
```vb#  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Идентификатор ошибки:** BC33107  
  
### Чтобы исправить эту ошибку  
  
-   Если не удается изменить код так, чтобы первым аргумент являлся ссылочным типом или поддерживал значение NULL, рассмотрите возможность преобразования к выражению `If` с тремя аргументами или к оператору `If...Then...Else`.  
  
    ```vb#  
    Console.WriteLine(If(choice1 < choice2, 1, 2))  
    Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
    ```  
  
## См. также  
 [Оператор If](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Типы значения, допускающие Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)