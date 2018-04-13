---
title: Практическое руководство. Создание коллекции, используемой инициализатором набора (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cff862f16530bc268628d9406ae81d23f2761926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Практическое руководство. Создание коллекции, используемой инициализатором набора (Visual Basic)
При использовании инициализатора коллекции для создания коллекции, компилятор Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе коллекции. Это `Add` метод используется для заполнения коллекции со значениями из инициализатора коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере показан `OrderCollection` коллекцию, которая содержит открытый `Add` метод, который можно использовать инициализатор коллекции для добавления объектов типа `Order`. `Add` Метод дает возможность использовать сокращенный синтаксис инициализатора набора.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
