---
title: Me, My, MyBase и MyClass в Visual Basic
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
ms.openlocfilehash: 7df146e09a1d7cd730f4cf539d6823f7ced44bd1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002531"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase и MyClass в Visual Basic
`Me`, `My`, `MyBase` и `MyClass` в Visual Basic имеют похожие имена, но разные цели. В этом разделе описывается каждая из этих сущностей, чтобы их можно было отличать.  
  
## <a name="me"></a>Me  
 Ключевое слово `Me` позволяет ссылаться на конкретный экземпляр класса или структуры, в которой в данный момент выполняется код. `Me` ведет себя как либо переменная объекта, либо переменная структуры, ссылающаяся на текущий экземпляр. Использование `Me` особенно полезно для передачи сведений о текущем выполняющемся экземпляре класса или структуры в процедуру в другом классе, структуре или модуле.  
  
 Например, предположим, что в модуле имеется следующая процедура.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Эту процедуру можно вызвать и передать текущий экземпляр класса <xref:System.Windows.Forms.Form> в качестве аргумента с помощью следующей инструкции.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My - функция  
 Функция `My` обеспечивает простой и интуитивно понятный доступ к ряду .NET Framework классов, позволяя Visual Basic пользователю взаимодействовать с компьютером, приложением, параметрами, ресурсами и т. д.  
  
## <a name="mybase"></a>Слово  
 Ключевое слово `MyBase` ведет себя как объектная переменная, ссылающаяся на базовый класс текущего экземпляра класса. `MyBase` обычно используется для доступа к членам базового класса, которые переопределяются или переобъявляются в производном классе. `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
## <a name="myclass"></a>MyClass  
 Ключевое слово `MyClass` ведет себя как объектная переменная, ссылающаяся на текущий экземпляр класса как изначально реализованный. `MyClass` аналогична `Me`, но все вызовы методов в нем обрабатываются так, как если бы метод был `NotOverridable`.  
  
## <a name="see-also"></a>См. также

- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
