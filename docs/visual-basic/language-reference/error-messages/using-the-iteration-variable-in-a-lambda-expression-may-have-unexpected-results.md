---
title: Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 358c7a988ae95c2326a26bc048f5436e11acb340
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641594"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам
Использование переменной итерации в лямбда-выражение может иметь непредвиденные результаты. Вместо этого создайте локальную переменную в цикле и присвойте ей значение переменной итерации.  
  
 Это предупреждение появляется при использовании переменной итерации цикла, объявленная внутри цикла лямбда-выражение. Например следующий пример вызывает предупреждение выводится.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 В следующем примере непредвиденные результаты, которые могут возникнуть.  
  
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
  
 `For` Создает массив лямбда-выражений, каждый из которых возвращает значение переменной итерации цикла, цикл `i`. При вычислении лямбда-выражения в `For Each` цикл, могут ожидать см. в разделе 0, 1, 2, 3 и 4, последовательных значений `i` в `For` цикла. Вместо этого отображается конечное значение `i` отображаются пять раз:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42324  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Назначьте переменной итерации в локальной переменной и используйте локальную переменную в лямбда-выражения.  
  
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
- [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
