---
title: Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 5e35ad80037e843fd3cbd9caa68dcb2a09d707e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)
При использовании инициализатора коллекции для создания коллекции, компилятор Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе коллекции. Это `Add` метод используется для заполнения коллекции со значениями из инициализатора коллекции.  
  
 Если совпадений `Add` метод существует и не может изменить код для коллекции, можно добавить метод расширения вызывается `Add` с параметрами, которые требуются в инициализаторе коллекции. Обычно это необходимо делать, если использовать инициализаторы коллекции для универсальных коллекций.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует добавление метода расширения к универсальному <xref:System.Collections.Generic.List%601> тип, так что можно использовать инициализатор коллекции для добавления объектов определенного типа `Employee`. Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
