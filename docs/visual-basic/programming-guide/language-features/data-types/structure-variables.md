---
title: "Переменные структуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "переменные структуры"
  - "структуры, переменные структуры"
  - "структуры, переменные"
  - "переменные [Visual Basic], переменные структуры"
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Переменные структуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

После создания структуры можно объявлять переменные на уровне процедур и модулей как указанный тип.  Например, можно создать структуру, которая записывает сведения о компьютере.  Это показано в приведенном ниже примере.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Можно объявить переменные этого типа.  Это показано в следующих объявлениях.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  В классах и модулях по умолчанию глобальные структуры объявляются с помощью [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  Если структура должна быть закрытой, необходимо объявить ее с помощью ключевого слова [Private](../../../../visual-basic/language-reference/modifiers/private.md).  
  
## Доступ к значениям структуры  
 Для присвоения и извлечения значений элементов переменных структуры используется тот же синтаксис, что и для задания и получения свойств объекта.  Оператор доступа к члену \(`.`\) следует помещать между именем переменной структуры и именем элемента.  В следующих примерах демонстрируется доступ к элементам переменных, ранее объявленных как тип `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## Присваивание переменных структуры  
 Можно также присвоить одну переменную другой, имеющей такой же тип структуры.  В этом случае происходит копирование всех элементов одной структуры в соответствующие элементы другой.  Это показано в следующих объявлениях.  
  
```  
yourSystem = mySystem  
```  
  
 Если элементы структуры являются ссылочными типами \(например `String`, `Object` или массивом\), копируется указатель на данные.  В предыдущем примере, если `systemInfo` содержит переменную объекта, то копируется указатель из `mySystem` в `yourSystem`, и изменение данных объекта через одну структуру вступает в силу при доступе через другую структуру.  
  
## См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Структуры и другие элементы программирования](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Структуры и классы](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)