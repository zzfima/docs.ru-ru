---
title: "Структуры и другие элементы программирования (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "массивы [Visual Basic], элементы структуры"
  - "вложенные структуры"
  - "объекты [Visual Basic], элементы структуры"
  - "процедуры, структуры в качестве аргументов"
  - "структуры, массивы"
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Структуры и другие элементы программирования (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Структуры можно использовать вместе с массивами, объектами, процедурами и другими структурами.  При взаимодействии применяется тот же синтаксис, который используется этими элементами по отдельности.  
  
> [!NOTE]
>  Невозможна инициализация каких\-либо элементов структуры в объявлении структуры.  Значения могут быть присвоены только тем элементам переменной, которые объявлены в качестве типа структуры.  
  
## Структуры и массивы  
 Структура может содержать массив в качестве одного или нескольких элементов.  Это показано в приведенном ниже примере.  
  
```vb#  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 Доступ к значениям массива внутри структуры осуществляется тем же способом, что и доступ к свойству в объекте.  Это показано в приведенном ниже примере.  
  
```vb#  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Можно также объявить массив структур.  Это показано в приведенном ниже примере.  
  
```vb#  
Dim allSystems(100) As systemInfo  
```  
  
 Действуют те же правила для доступа к компонентам этой архитектуры данных.  Это показано в приведенном ниже примере.  
  
```vb#  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## Структуры и объекты  
 Структура может содержать объект в качестве одного или нескольких элементов.  Это показано в приведенном ниже примере.  
  
```vb#  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 В таком объявлении следует указать определенный класс объекта, а не просто `Object`.  
  
## Структуры и процедуры  
 Структуру можно передать в качестве аргумента процедуры.  Это показано в приведенном ниже примере.  
  
```vb#  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 В предыдущем примере структура передается *по ссылке*, что позволяет изменять элементы процедуры, чтобы изменения применялись к вызывающему коду.  Чтобы защитить структуру от такого изменения, ее следует передавать по значению.  
  
 Можно также вернуть структуру из процедуры `Function`.  Это показано в приведенном ниже примере.  
  
```vb#  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## Структуры внутри структур  
 Структуры могут содержать другие структуры.  Это показано в приведенном ниже примере.  
  
```vb#  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb#  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 Эту методику можно использовать для включения структуры, определенной в одном модуле, в структуру, определенную в другом модуле.  
  
 Структуры могут быть вложены друг в друга в произвольном порядке.  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Переменные структуры](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)