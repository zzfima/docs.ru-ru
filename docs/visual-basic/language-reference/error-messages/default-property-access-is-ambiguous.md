---
title: 'При доступе к свойству по умолчанию возникает неоднозначность между членами наследуемых интерфейсов: <defaultpropertyname> интерфейса <interfacename1> и <defaultpropertyname> интерфейса <interfacename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5f058c8e7d480b9145452ae85f186a6ac2ed0d56
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836354"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>Доступ к свойству по умолчанию определяется неоднозначно между членами наследуемых интерфейсов\<defaultpropertyname > "интерфейса"\<имя_интерфейса1 > "и"\<defaultpropertyname > "интерфейса"\< имя_интерфейса2 > "
Интерфейс наследует от двух интерфейсов, каждый из которых объявляет свойство по умолчанию с тем же именем. Компилятор не может разрешить доступ к этому свойству значение по умолчанию без указания полного имени. Это показано в следующем примере.  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 При указании `testObj(1)`, компилятор пытается разрешить его в свойство по умолчанию. Тем не менее существуют два свойства по умолчанию из-за наследуемых интерфейсов, поэтому компилятор создает эту ошибку.  
  
 **Идентификатор ошибки:** BC30686  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Избегайте наследования элементов с одинаковым именем. В предыдущем примере если `testObj` не требуется ни один из членов, скажем, `Iface2`, объявите ее следующим образом:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     - или -  
  
-   Реализуйте наследуемый интерфейс в классе. Затем можно реализовать все наследуемые свойства с разными именами. Однако только один из них может быть свойство по умолчанию, реализующего класса. Это показано в следующем примере.  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a>См. также

- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
