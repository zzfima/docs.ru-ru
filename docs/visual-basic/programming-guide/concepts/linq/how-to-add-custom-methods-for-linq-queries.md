---
title: "Практическое руководство: Добавление пользовательских методов для запросов LINQ (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>Практическое руководство: Добавление пользовательских методов для запросов LINQ (Visual Basic)
Можно расширить набор методов, которые можно использовать для запросов LINQ путем добавления методов расширения в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601> Например Помимо стандартных среднее или максимальное число операций, можно создать настраиваемый статистический метод для вычисления одного значения на основе последовательности значений. Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность. Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>и <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A>  
  
 При расширении <xref:System.Collections.Generic.IEnumerable%601>интерфейс, пользовательские методы можно применять к любой перечислимой коллекции.</xref:System.Collections.Generic.IEnumerable%601> Дополнительные сведения см. в разделе [методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="adding-an-aggregate-method"></a>Добавление статистического метода  
 Статистический метод вычисляет одно значение из набора значений. LINQ предоставляет несколько статистических методов, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>и <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A> Статистический метод можно создать путем добавления метода расширения в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601>  
  
 В следующем примере кода показано, как создать метод расширения `Median` для вычисления медианы последовательности чисел типа `double`.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 Этот метод расширения вызывается для любой перечислимой коллекции в так же, как и другие статистические методы из <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601>  
  
> [!NOTE]
>  В Visual Basic можно использовать вызов метода или стандартный синтаксис запроса для `Aggregate` или `Group By` предложения. Дополнительные сведения см. в разделе [предложения Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 В следующем примере кода показано, как использовать `Median` метод массивом типа `double`.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Перегрузка статистического метода для принятия различных типов  
 Статистический метод можно перегрузить, чтобы он принимал последовательности различных типов. Стандартный подход — создание перегрузки для каждого типа. Другой подход заключается в создании перегрузки, которая будет принимать универсального типа и преобразуют его в конкретный тип с помощью делегата. Также можно сочетать оба подхода.  
  
#### <a name="to-create-an-overload-for-each-type"></a>Создание перегрузки для каждого типа  
 Можно создать определенные перегрузки для каждого типа, который требуется поддерживать. В следующем примере кода показана перегрузка `Median` метод `integer` типа.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Теперь можно вызвать `Median` перегрузки для обоих `integer` и `double` типов, как показано в следующем коде:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
#### <a name="to-create-a-generic-overload"></a>Чтобы создать универсальную перегрузку  
 Можно также создать перегрузку, которая принимает последовательность универсальных объектов. Эта перегрузка принимает делегат в качестве параметра и применяет его для преобразования последовательности объектов универсального типа для конкретного типа.  
  
 В следующем коде показано перегрузку `Median` метода, принимающего <xref:System.Func%602>делегат в качестве параметра.</xref:System.Func%602> Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 Теперь можно вызвать `Median` метод для последовательности объектов любого типа. Если тип не имеет свой собственный перегруженный метод, необходимо передать параметр-делегат. В Visual Basic можно использовать лямбда-выражение для этой цели. Кроме того при использовании `Aggregate` или `Group By` предложение вместо вызова метода можно передать любое значение или выражение, которое находится в области видимости этого предложения.  
  
 В следующем примере кода показано, как вызвать `Median` метод массив целых чисел и массива строк. Для строк вычисляется Медиана длин строк в массиве. В примере для передачи <xref:System.Func%602>параметр-делегат `Median` метод для каждого случая.</xref:System.Func%602>  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
## <a name="adding-a-method-that-returns-a-collection"></a>Добавление метода, возвращающего коллекцию  
 Вы можете расширить <xref:System.Collections.Generic.IEnumerable%601>интерфейса с помощью пользовательского запроса метода, который возвращает последовательность значений.</xref:System.Collections.Generic.IEnumerable%601> В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> Эти методы можно использовать для применения фильтров или преобразований данных к последовательности значений.  
  
 Приведенный ниже показано, как создать метод расширения с именем `AlternateElements` , возвращает каждый второй элемент в коллекции, начиная с первого элемента.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 Этот метод расширения можно вызвать для любой перечислимой коллекции так же, как и другие методы из <xref:System.Collections.Generic.IEnumerable%601>интерфейс, как показано в следующем коде:</xref:System.Collections.Generic.IEnumerable%601>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
