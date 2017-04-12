---
title: "Использование переменной итератора в лямбда-выражение может иметь непредвиденные результаты | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5b293ec344d816e40d369757fa4d11710b7ecd8d
ms.lasthandoff: 03/13/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам
Использование переменной итерации в лямбда-выражении может привести к непредусмотренным результатам. Вместо этого создайте локальную переменную в цикле и присвойте ей значение переменной итерации.  
  
 Это предупреждение появляется при использовании переменной итерации цикла в лямбда-выражение, объявленная внутри цикла. Например приведенный ниже приводят к выводу предупреждения.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 В следующем примере показано непредвиденные результаты, которые могут возникнуть.  
  
```vb  
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
  
 `For` Цикла создает массив лямбда-выражений, каждое из которых возвращает значение переменной итерации цикла `i`. Когда лямбда-выражения вычисляются в `For Each` цикла может ожидать появления 0, 1, 2, 3 и 4, последовательных значений `i` в `For` цикла. Вместо этого, вы увидите итоговое значение `i` отображается пять раз:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42324  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Присвойте значение переменной итерации локальной переменной и используйте локальную переменную в лямбда-выражение.  
  
```vb  
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
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
