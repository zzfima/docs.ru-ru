---
title: 'При доступе к свойству по умолчанию возникает неоднозначность между членами наследуемых интерфейсов: <defaultpropertyname> интерфейса <interfacename1> и <defaultpropertyname> интерфейса <interfacename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: a36cfe8e5496bbfd1941afa8a46086491ae96a2a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512750"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>Неоднозначность доступа к свойству по умолчанию между\<унаследованными членами интерфейса "дефаултпропертинаме\<>" интерфейса "interfacename1\<>" и "дефаултпропертинаме >\< " интерфейса " interfacename2 > "

Интерфейс наследует от двух интерфейсов, каждый из которых объявляет свойство по умолчанию с тем же именем. Компилятор не может разрешить доступ к этому свойству по умолчанию без уточнения. Это показано в следующем примере.

```vb
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

При указании `testObj(1)`компилятор пытается разрешить его в свойство по умолчанию. Однако существует два возможных свойства по умолчанию из-за наследуемых интерфейсов, поэтому компилятор сообщает об этой ошибке.

**Идентификатор ошибки:** BC30686

## <a name="to-correct-this-error"></a>Исправление ошибки

- Избегайте наследования членов с одинаковыми именами. В предыдущем примере, если `testObj` не требуется ни один из членов, скажем, `Iface2`, объявить его следующим образом:

  ```vb
  Dim testObj As Iface1
  ```

  \-или-

- Реализуйте наследуемый интерфейс в классе. Затем можно реализовать каждое из наследуемых свойств с разными именами. Однако только один из них может быть свойством по умолчанию реализующего класса. Это показано в следующем примере.

  ```vb
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
