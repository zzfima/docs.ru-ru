---
title: Практическое руководство. Создание метода расширения Add, используемого инициализатором набора
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346711"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)
При использовании инициализатора коллекции для создания коллекции компилятор Visual Basic выполняет поиск метода `Add` типа коллекции, параметры которого соответствуют типам значений в инициализаторе коллекции с помощью параметров метода `Add`. Этот метод `Add` используется для заполнения коллекции значениями из инициализатора коллекции.  
  
 Если соответствующий метод `Add` не существует и вы не можете изменить код для коллекции, можно добавить метод расширения с именем `Add`, который принимает параметры, необходимые инициализатору коллекции. Обычно это необходимо сделать при использовании инициализаторов коллекций для универсальных коллекций.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как добавить метод расширения в универсальный тип <xref:System.Collections.Generic.List%601>, чтобы инициализатор коллекции можно было использовать для добавления объектов типа `Employee`. Метод расширения позволяет использовать сокращенный синтаксис инициализатора коллекции.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Инициализаторы коллекций](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
