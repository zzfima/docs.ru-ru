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
ms.openlocfilehash: f3db5f8f6688e68992f683ac1b1465078aa41231
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244716"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase и MyClass в Visual Basic
`Me`, `My`, `MyBase`, и `MyClass` в Visual Basic имеют одинаковые имена, но предназначены для разных целей. В этом разделе описан каждый из этих сущностей, чтобы отличать их.  
  
## <a name="me"></a>Me  
 `Me` Ключевое слово предоставляет возможность ссылаться на конкретный экземпляр класса или структуры, в котором в данный момент выполняется код. `Me` ведет себя как объектную переменную или переменную структуры, ссылка на текущий экземпляр. С помощью `Me` особенно полезна для передачи сведений о текущий выполняемый экземпляр класса или структуры в процедуру в другой класс, структуру или модуля.  
  
 Например предположим, что у вас есть следующие действия в модуле.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Можно вызвать эту процедуру и передать текущий экземпляр <xref:System.Windows.Forms.Form> класса как аргумент с помощью следующей инструкции.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My - функция  
 `My` Компонент предоставляет простой и понятный доступ к определенным [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] классов, позволяя пользователям Visual Basic для взаимодействия с компьютера, приложения, параметры, ресурсы и т. д.  
  
## <a name="mybase"></a>MyBase  
 `MyBase` Ключевое слово ведет себя как объектной переменной, ссылающейся на базовый класс текущего экземпляра класса. `MyBase` обычно используется для доступа к членам базового класса, переопределены или скрыты в производном классе. `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
## <a name="myclass"></a>MyClass  
 `MyClass` Ключевое слово ведет себя как объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован. `MyClass` аналогичен `Me`, но все вызовы методов на нем рассматриваются, как если бы метод был `NotOverridable`.  
  
## <a name="see-also"></a>См. также  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
