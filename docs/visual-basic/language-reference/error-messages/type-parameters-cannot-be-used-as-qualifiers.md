---
title: "Параметры типа нельзя использовать в качестве квалификаторов | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32098"
  - "bc32098"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32098"
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Параметры типа нельзя использовать в качестве квалификаторов
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Элемент программирования уточнен строкой квалификации, которая включает параметр\-тип.  
  
 Параметр\-тип представляет требование, которое должно быть предоставлено при создании универсального типа.  Он не представляет конкретный определенный тип.  Строка квалификации должна включать только элементы, определенные во время компиляции.  
  
 Эту ошибку могут вызвать следующие инструкции.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Идентификатор ошибки:** BC32098  
  
### Чтобы исправить эту ошибку  
  
1.  Удалите параметр\-тип из строки квалификации или замените его определенным типом.  
  
2.  Если для обнаружения квалифицируемого элемента программирования требуется использование сконструированного типа, необходимо использовать дополнительную логику программы.  
  
## См. также  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)