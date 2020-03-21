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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401433"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase и MyClass в Visual Basic
`Me`, `My` `MyBase`, `MyClass` , и в Visual Basic имеют похожие названия, но разные цели. Эта тема описывает каждый из этих сущностей для того, чтобы различать их.  
  
## <a name="me"></a>У меня  
 Ключевое `Me` слово предоставляет способ отсылки к конкретному экземпляру класса или структуры, в котором код в настоящее время исполняется. `Me`ведет себя как переменная объекта или переменная структуры, относящаяся к текущему экземпляру. Использование `Me` особенно полезно для передачи информации о данном экземпляре выполнения класса или структуры процедуре в другом классе, структуре или модуле.  
  
 Например, предположим, что в модуле есть следующая процедура.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Вы можете вызвать эту процедуру <xref:System.Windows.Forms.Form> и передать текущий экземпляр класса в качестве аргумента, используя следующее утверждение.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Функция `My` обеспечивает простой и интуитивно понятный доступ к ряду классов .NET Framework, позволяя пользователю Visual Basic взаимодействовать с компьютером, приложением, настройками, ресурсами и так далее.  
  
## <a name="mybase"></a>MyBase  
 Ключевое `MyBase` слово ведет себя как объектная переменная, относящаяся к базовому классу текущего экземпляра класса. `MyBase`обычно используется для доступа к членам базового класса, которые переопределены или затенены в производных классах. `MyBase.New`используется для явного вызова конструктора базового класса из производного конструктора класса.  
  
## <a name="myclass"></a>MyClass  
 Ключевое `MyClass` слово ведет себя как объектная переменная, относящаяся к текущему экземпляру класса в первоначальнореализованном виде. `MyClass`похож на `Me`, но все методы звонки на `NotOverridable`него рассматриваются как если бы метод был .  
  
## <a name="see-also"></a>См. также раздел

- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
