---
title: Me, My, MyBase и MyClass в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d06c97bdf4824e878d617b2d09993d18c60336b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase и MyClass в Visual Basic
`Me`, `My`, `MyBase`, и `MyClass` в Visual Basic имеют схожие имена, но для других целей. В этом разделе описан каждый из этих сущностей, чтобы отличать их.  
  
## <a name="me"></a>Me  
 `Me` Ключевое слово предоставляет способ ссылки на определенный экземпляр класса или структуры, в котором в данный момент выполняется код. `Me` ведет себя подобно объектной или структурной переменной, ссылающейся на текущий экземпляр. С помощью `Me` особенно полезен для передачи данных о текущей выполняемой экземпляра класса или структуры в процедуру в другой класс, структура или модуль.  
  
 Например рассмотрим следующую процедуру в модуле.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Можно вызвать эту процедуру и передать текущий экземпляр <xref:System.Windows.Forms.Form> класса в качестве аргумента, используя следующую инструкцию.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My - функция  
 `My` Обеспечивает простой и понятный доступ на ряд [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] классов, позволяя пользователям Visual Basic для взаимодействия с компьютера, приложения, параметры, ресурсы и т. д.  
  
## <a name="mybase"></a>MyBase  
 `MyBase` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра класса. `MyBase` обычно используется для доступа к членам базового класса, которые переопределены или скрыты в производном классе. `MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.  
  
## <a name="myclass"></a>MyClass  
 `MyClass` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован. `MyClass` Аналогично `Me`, но все вызовы методов на нем рассматриваются, как если бы метод `NotOverridable`.  
  
## <a name="see-also"></a>См. также  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
