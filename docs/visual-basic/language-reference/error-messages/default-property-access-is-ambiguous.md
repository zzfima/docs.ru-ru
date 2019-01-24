---
title: Доступ к свойству по умолчанию определяется неоднозначно между членами наследуемых интерфейсов &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса1&gt; &#39; и &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 1fae63506a35eb046676214a2b6c52977f24645d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518648"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a>Доступ к свойству по умолчанию определяется неоднозначно между членами наследуемых интерфейсов &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса1&gt; &#39; и &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса2&gt;&#39;
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
