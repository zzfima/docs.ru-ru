---
title: "Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42324"
  - "bc42324"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42324"
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Использование переменной итерации в лямбда\-выражении может привести к неожиданным результатам.Вместо этого создайте локальную переменную в пределах цикла и присвойте ей значение переменной итерации.  
  
 Это предупреждение возникает, когда вы используете переменную итерации цикла в лямбда\-выражении, объявленном внутри цикла.  Например, предупреждение выводится в следующем случае.  
  
```vb#  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 Приведенный пример демонстрирует возможный неожиданный результат.  
  
```vb#  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 Цикл `For` создает массив лямбда\-выражений, каждое из которых возвращает значение переменной итерации цикла `i`.  При оценке лямбда\-выражений в цикле `For Each` ожидается появление значений 0, 1, 2, 3 или 4, т.е. последовательных значений `i` в цикле `For`.  Но, вместо этого пять раз подряд выводится окончательное значение `i`:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42324  
  
### Чтобы исправить эту ошибку  
  
-   Назначьте локальной переменной значение переменной итерации и используйте локальную переменную в лямбда\-выражении.  
  
    ```vb#  
    Module Module1  
        Sub Main()  
            Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
            For i As Integer = 0 To 4  
                Dim j = i  
                array1(i) = Function() j  
            Next  
  
            For Each funcElement In array1  
                System.Console.WriteLine(funcElement())  
            Next  
  
        End Sub  
    End Module  
    ```  
  
## См. также  
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)