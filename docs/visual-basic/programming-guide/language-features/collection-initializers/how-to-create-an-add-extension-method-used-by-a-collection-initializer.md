---
title: Как выполнить Создание метода Add, расширение используемого инициализатором набора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 3a1db8ede8162b329d546c0e712ef1c2df7d7883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661676"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Как выполнить Создание метода Add, расширение используемого инициализатором набора (Visual Basic)
При использовании инициализатора коллекции для создания коллекции, используемые компилятором Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе набора. Это `Add` метод используется для заполнения коллекции значениями из инициализатора коллекции.  
  
 Если совпадающих `Add` метод существует и не может изменить код для коллекции, можно добавить метод расширения `Add` с параметрами, которые требуются для инициализатора набора. Обычно это необходимо выполнить с помощью инициализаторов коллекций для универсальных коллекций.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как добавить метод расширения к общим <xref:System.Collections.Generic.List%601> так, чтобы инициализатора коллекции можно использовать для добавления объектов определенного типа `Employee`. Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>См. также
- [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
