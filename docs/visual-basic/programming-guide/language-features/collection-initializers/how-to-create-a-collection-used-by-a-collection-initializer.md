---
title: Практическое руководство. Создание коллекции, используемой инициализатором набора
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 5eaf9e828455bf2accda86ab52a1ce645f10b9ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349053"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Практическое руководство. Создание коллекции, используемой инициализатором набора (Visual Basic)
При использовании инициализатора коллекции для создания коллекции компилятор Visual Basic выполняет поиск метода `Add` типа коллекции, параметры которого соответствуют типам значений в инициализаторе коллекции с помощью параметров метода `Add`. Этот метод `Add` используется для заполнения коллекции значениями из инициализатора коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере показана коллекция `OrderCollection`, содержащая открытый метод `Add`, который инициализатор коллекции может использовать для добавления объектов типа `Order`. Метод `Add` позволяет использовать сокращенный синтаксис инициализатора коллекции.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
