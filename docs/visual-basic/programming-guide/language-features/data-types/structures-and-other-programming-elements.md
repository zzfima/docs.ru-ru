---
title: Структуры и другие элементы программирования
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266863"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Структуры и другие элементы программирования (Visual Basic)
Вы можете использовать структуры в сочетании с массивами, объектами и процедурами, а также друг с другом. Взаимодействия используют тот же синтаксис, что и эти элементы по отдельности.  
  
> [!NOTE]
> Нельзя инициализировать ни один из элементов структуры в декларации структуры. Значения можно присваивать только элементам переменной, которая была объявлена типом структуры.  
  
## <a name="structures-and-arrays"></a>Структуры и массивы  
 Структура может содержать массив как один или несколько его элементов. Это показано в следующем примере.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 Вы получаете доступ к значениям массива в структуре так же, как вы получаете доступ к свойству на объекте. Это показано в следующем примере.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Вы также можете объявить массив структур. Это показано в следующем примере.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Доступ к компонентам этой архитектуры данных соблюдается тем и тем и тем и тем и тем образом. Это показано в следующем примере.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Структуры и объекты  
 Структура может содержать объект как один или несколько его элементов. Это показано в следующем примере.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 В таком заявлении следует использовать определенный `Object`класс объектов, а не .  
  
## <a name="structures-and-procedures"></a>Структуры и процедуры  
 Вы можете передать структуру в качестве процедурного аргумента. Это показано в следующем примере.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Предыдущий пример передает структуру *по ссылке,* что позволяет процедуре изменять свои элементы таким образом, чтобы изменения вступили в силу в вызывающем коде. Если вы хотите защитить конструкцию от такой модификации, передайте ее по стоимости.  
  
 Вы также можете вернуть `Function` структуру из процедуры. Это показано в следующем примере.  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a>Структуры внутри структур  
 Структуры могут содержать другие структуры. Это показано в следующем примере.  
  
```vb  
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
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 Вы также можете использовать этот метод для инкапсулирования структуры, определенной в одном модуле в структуре, определенной в другом модуле.  
  
 Структуры могут содержать другие структуры на произвольной глубине.  
  
## <a name="see-also"></a>См. также раздел

- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Переменные структуры](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
