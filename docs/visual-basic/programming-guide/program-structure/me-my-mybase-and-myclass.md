---
title: Me, My, MyBase и MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347340"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase и MyClass в Visual Basic
`Me`, `My`, `MyBase`и `MyClass` в Visual Basic имеют похожие имена, но разные цели. В этом разделе описывается каждая из этих сущностей, чтобы их можно было отличать.  
  
## <a name="me"></a>Me  
 Ключевое слово `Me` предоставляет способ обращения к конкретному экземпляру класса или структуры, в котором в данный момент выполняется код. `Me` ведет себя как либо переменная объекта, либо переменная структуры, ссылающаяся на текущий экземпляр. Использование `Me` особенно полезно для передачи сведений о текущем выполняющемся экземпляре класса или структуры в процедуру в другом классе, структуре или модуле.  
  
 Например, предположим, что в модуле имеется следующая процедура.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Вы можете вызвать эту процедуру и передать текущий экземпляр класса <xref:System.Windows.Forms.Form> в качестве аргумента с помощью следующей инструкции.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My - функция  
 Функция `My` предоставляет простой и интуитивно понятный доступ к ряду .NET Framework классов, позволяя Visual Basic пользователю взаимодействовать с компьютером, приложением, параметрами, ресурсами и т. д.  
  
## <a name="mybase"></a>Слово  
 Ключевое слово `MyBase` ведет себя как объектная переменная, ссылающаяся на базовый класс текущего экземпляра класса. `MyBase` обычно используется для доступа к членам базового класса, которые переопределяются или переобъявляются в производном классе. `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
## <a name="myclass"></a>MyClass  
 Ключевое слово `MyClass` ведет себя как объектная переменная, ссылающаяся на текущий экземпляр класса как изначально реализованный. `MyClass` похож на `Me`, но все вызовы методов в нем обрабатываются так, как если бы метод был `NotOverridable`.  
  
## <a name="see-also"></a>См. также

- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
