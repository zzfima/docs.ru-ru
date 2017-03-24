---
title: "Ковариация и контравариация (Visual Basic) | Документы Microsoft"
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
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
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
ms.openlocfilehash: b785e298c5ba38a8e3d8cc549b2dcf2df1ef6bd8
ms.lasthandoff: 03/13/2017

---
# <a name="covariance-and-contravariance-visual-basic"></a>Ковариация и контравариация (Visual Basic)
В Visual Basic Ковариация и контрвариация включить неявное преобразование ссылок для типов массивов, типы делегатов и аргументы универсального типа. Ковариантность сохраняет совместимость назначения, а контрвариантность заменяет ее на обратную.  
  
 Следующий код демонстрирует разница между совместимостью назначения, Ковариация и контрвариация.  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 Ковариация массивов позволяет выполнять неявное преобразование массив производного типа в массив менее производный тип. Но эта операция не является типобезопасным, как показано в следующем примере кода.  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 Ковариация и контравариация поддержка групп методов позволяет при сопоставлении сигнатур методов с типами делегатов. Это позволяет вам назначать делегатам не только методы, которые обладают соответствующими сигнатурами, но и методы, которые возвращают более производные типы (ковариация), или, принимают параметры, которые имеют менее производные типы (контравариация), чем указано в типе делегата. Дополнительные сведения см. в разделе [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [с помощью Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
 В следующем примере кода показан метод групп поддержки ковариации и контравариации.  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 В .NET Framework 4 или более поздней версии Visual Basic поддерживают ковариантность и контрвариантность в универсальных интерфейсах и делегатах и позволяют выполнять неявное преобразование параметров универсального типа. Дополнительные сведения см. в разделе [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) и [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
 В следующем примере кода показано неявное преобразование ссылочного типа для универсальных интерфейсов.  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 Универсальный интерфейс или делегат называется *вариант* если его универсальные параметры объявлены как ковариантные или контравариантные. Visual Basic позволяет создавать собственные вариантные интерфейсы и делегаты. Дополнительные сведения см. в разделе [Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) и [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|В этом разделе описываются ковариация и контрвариация в универсальных интерфейсах, а также представлен список вариативных универсальных интерфейсов платформы .NET Framework.|  
|[Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|Показано, как создавать пользовательские интерфейсы variant.|  
|[Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|Описание использования поддержки ковариации и контравариации в <xref:System.Collections.Generic.IEnumerable%601>и <xref:System.IComparable%601>интерфейсы могут помочь повторного использования кода.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|[Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|Описание ковариации и контравариации в универсальных и неуниверсальных делегатах и предоставляет список вариативных универсальных методов-делегатов в платформе .NET Framework.|  
|[Использование вариативности в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|Показано, как использовать поддержку ковариации и контравариации в неуниверсальных методов-делегатов при сопоставлении сигнатуры метода с типами делегатов.|  
|[Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|Описание использования поддержки ковариации и контравариации в `Func` и `Action` делегаты могут помочь повторного использования кода.|
