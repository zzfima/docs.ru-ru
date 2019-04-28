---
title: Практическое руководство. Создание метода Add, расширение используемого инициализатором набора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907079"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Практическое руководство. Создание метода Add, расширение используемого инициализатором набора (Visual Basic)
При использовании инициализатора коллекции для создания коллекции, используемые компилятором Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе набора. Это `Add` метод используется для заполнения коллекции значениями из инициализатора коллекции.  
  
 Если совпадающих `Add` метод существует и не может изменить код для коллекции, можно добавить метод расширения `Add` с параметрами, которые требуются для инициализатора набора. Обычно это необходимо выполнить с помощью инициализаторов коллекций для универсальных коллекций.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как добавить метод расширения к общим <xref:System.Collections.Generic.List%601> так, чтобы инициализатора коллекции можно использовать для добавления объектов определенного типа `Employee`. Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
