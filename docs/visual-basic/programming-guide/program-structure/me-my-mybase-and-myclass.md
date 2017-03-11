---
title: "Me, My, MyBase и MyClass в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "MyClass"
  - "vb.Me"
  - "MyBase"
  - "vb.MyBase"
  - "Me"
  - "vb.MyClass"
  - "vb.This"
  - "vb.My"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "текущий экземпляр, Me - ключевое слово"
  - "Me - ключевое слово"
  - "Me - ключевое слово, ссылка на текущий экземпляр объекта"
  - "Me - ключевое слово, связь с одинаковыми элементами программирования"
  - "My - объект"
  - "MyBase - ключевое слово, связь с одинаковыми элементами программирования"
  - "MyClass - ключевое слово, связь с одинаковыми элементами программирования"
  - "ссылка на себя"
  - "ссылка на себя, Me - ключевое слово"
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Me, My, MyBase и MyClass в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Сущности `Me`, `My`, `MyBase` и `MyClass` в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] имеют похожие имена, но различные цели.  Этот раздел описывает каждую из этих сущностей, чтобы их можно было различать.  
  
## Me  
 Ключевое слово `Me` предоставляет способ ссылки на отдельный экземпляр класса или структуры, где в текущий момент выполняется код.  Ключевое слово `Me` ведет себя подобно объектной или структурной переменной, ссылающейся на текущий экземпляр.  Ключевое слово `Me` особенно полезно для передачи данных о выполняющемся в данный момент экземпляре класса или структуры в процедуру, находящуюся в другом классе, структуре или модуле.  
  
 Предположим, например, что в модуле имеется следующая процедура:  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Вызвать эту процедуру и передать в качестве аргумента текущий экземпляр класса <xref:System.Windows.Forms.Form> можно с помощью следующей инструкции.  
  
```  
ChangeFormColor(Me)  
```  
  
## My  
 `My` обеспечивает простой и понятный доступ к ряду классов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], позволяя пользователю [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] взаимодействовать с компьютером, приложением, настройками, ресурсами и т. д.  
  
## MyBase  
 Ключевое слово `MyBase` ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра.  Ключевое слово `MyBase` обычно используется для обращения к членам базового класса, которые переопределены или скрыты в производном классе.  Обращением `MyBase.New` можно воспользоваться для явного вызова конструктора базового класса из конструктора производного класса.  
  
## MyClass  
 Ключевое слово `MyClass` ведет себя подобно объектной переменной, ссылающейся текущий экземпляр класса, который был изначально реализован.  Ключевое слово `MyClass` аналогично ключевому слову `Me`, но при этом все вызовы методов рассматриваются, как если бы методы относились к типу `NotOverridable`.  
  
## См. также  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)