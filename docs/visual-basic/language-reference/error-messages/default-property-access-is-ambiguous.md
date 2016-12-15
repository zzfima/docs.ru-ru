---
title: "При доступе к свойству по умолчанию возникает неоднозначность между членами наследуемых интерфейсов: &lt;имяСвойстваПоУмолчанию&gt; интерфейса &lt;имяИнтерфейса1&gt; и &lt;имяСвойстваПоУмолчанию&gt; интерфейса &lt;имяИнтерфейса2&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30686"
  - "bc30686"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30686"
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# При доступе к свойству по умолчанию возникает неоднозначность между членами наследуемых интерфейсов: &lt;имяСвойстваПоУмолчанию&gt; интерфейса &lt;имяИнтерфейса1&gt; и &lt;имяСвойстваПоУмолчанию&gt; интерфейса &lt;имяИнтерфейса2&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Интерфейс наследуется из двух интерфейсов, каждый из которых объявляет свойство по умолчанию с тем же именем.  Компилятор не может разрешить доступ к этому свойству по умолчанию без уточнения.  Это показано в приведенном ниже примере.  
  
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
  
 При указании `testObj(1)` компилятор пытается разрешить его свойства по умолчанию.  Однако есть два возможных свойства по умолчанию, наследуемые из интерфейсов, поэтому компилятор создает эту ошибку.  
  
 **Идентификатор ошибки**: BC30686  
  
### Чтобы исправить эту ошибку  
  
-   Следует избегать наследования элементов с одинаковыми именами.  В предыдущем примере, если для `testObj` не требуется ни один из элементов из, например, `Iface2`, то он затем объявляется следующим образом:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     \-или\-  
  
-   Реализуйте наследуемый интерфейс в классе.  Затем можно реализовать все наследуемые свойства с различными именами.  Однако свойством по умолчанию в реализации класса может быть только одно из них.  Это показано в приведенном ниже примере.  
  
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
  
## См. также  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)