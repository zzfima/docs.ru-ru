---
title: "Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic) | Microsoft Docs"
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
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При использовании инициализатора набора для создания коллекции компилятор Visual Basic выполняет поиск метода `Add` типа коллекции, у которого параметры метода `Add` соответствуют типам значений в инициализаторе набора.  Этот метод `Add` служит для наполнения коллекции значениями из инициализатора набора.  
  
 Если подходящий метод `Add` не существует, а код коллекции изменить нельзя, то можно добавить метод расширения `Add` с параметрами, необходимыми для инициализатора набора.  Такие действия обычно необходимы при использовании инициализаторов наборов для создания универсальных коллекций.  
  
## Пример  
 В следующем примере показано, как добавить метод расширения к универсальному типу <xref:System.Collections.Generic.List%601>, чтобы инициализатор набора можно было использовать для добавления объектов типа `Employee`.  Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## См. также  
 [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)