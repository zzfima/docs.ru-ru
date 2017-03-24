---
title: "Me, My, MyBase и MyClass в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 59dba8961712537367db9a60e8b8ba68bcb6a1ea
ms.lasthandoff: 03/13/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase и MyClass в Visual Basic
`Me`, `My`, `MyBase`, и `MyClass` в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] имеют похожие имена, но для других целей. В этом разделе описан каждый из этих сущностей, чтобы различать их.  
  
## <a name="me"></a>Me  
 `Me` Ключевое слово предоставляет способ ссылки на определенный экземпляр класса или структуры, в котором в данный момент выполняется код. `Me`ведет себя подобно объектной или структурной переменной, ссылающейся на текущий экземпляр. С помощью `Me` особенно полезно для передачи данных о текущей выполняемой экземпляра класса или структуры в процедуру в другой класс, структура или модуль.  
  
 Например предположим, что в модуле имеется следующая процедура.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Можно вызвать эту процедуру и передать текущий экземпляр <xref:System.Windows.Forms.Form>класса в качестве аргумента, используя следующую инструкцию.</xref:System.Windows.Forms.Form>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My - функция  
 `My` Обеспечивает простой и понятный доступ на ряд [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] классов, включение [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] взаимодействие пользователя с компьютера, приложения, параметры, ресурсы и т. д.  
  
## <a name="mybase"></a>MyBase  
 `MyBase` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра класса. `MyBase`обычно используется для доступа к членам базового класса, которые переопределены или скрыты в производном классе. `MyBase.New`используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
## <a name="myclass"></a>MyClass  
 `MyClass` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован. `MyClass`Аналогично `Me`, но все вызовы методов рассматриваются, как если бы метод `NotOverridable`.  
  
## <a name="see-also"></a>См. также  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
