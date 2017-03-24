---
title: "Практическое руководство. Создание коллекции, используемой инициализатором набора (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "инициализаторы коллекций [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Практическое руководство. Создание коллекции, используемой инициализатором набора (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При использовании инициализатора набора для создания коллекции компилятор Visual Basic выполняет поиск метода `Add` типа коллекции, у которого параметры метода `Add` соответствуют типам значений в инициализаторе набора.  Этот метод `Add` служит для наполнения коллекции значениями из инициализатора набора.  
  
## Пример  
 В следующем примере показана коллекция `OrderCollection`, содержащая открытый метод `Add`, который может использоваться инициализатором набора для добавления объектов типа `Order`.  Метод `Add` позволяет использовать сокращенный синтаксис инициализатора набора.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## См. также  
 [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)