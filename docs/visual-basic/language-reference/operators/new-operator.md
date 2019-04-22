---
title: Оператор New (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 630b0c48def77449f426b287a26f95af7cfb930e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837737"
---
# <a name="new-operator-visual-basic"></a>Оператор New (Visual Basic)
Представляет `New` предложение, чтобы создать новый экземпляр объекта, задает для параметра типа ограничение конструктора, либо определяет `Sub` процедуры как конструктор класса.  
  
## <a name="remarks"></a>Примечания  
 В операторе объявления или назначения `New` предложение необходимо указать определенный класс, из которого может быть создан экземпляр. Это означает, что класс должен предоставлять один или несколько конструкторов, вызывающий код может получить доступ.  
  
 Можно использовать `New` предложение в операторе объявления или присваивания. При выполнении оператора вызывается соответствующий конструктор указанного класса, передав любые аргументы, заданные. В следующем примере показано это путем создания экземпляров `Customer` класс, который имеет два конструктора, который не принимает никаких параметров, а другой принимает строковый параметр.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Поскольку массивы являются классами, `New` можно создать новый экземпляр массива, как показано в следующих примерах.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Общеязыковая среда выполнения (CLR) создает <xref:System.OutOfMemoryException> ошибки, если недостаточно памяти для создания нового экземпляра.  
  
> [!NOTE]
>  `New` Ключевое слово также используется в списках параметров типа для указания, что тип должен предоставлять доступ к конструктору без параметров. Дополнительные сведения о параметров типа и ограничений, см. в разделе [список типов](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово. Дополнительные сведения см. в разделе [время жизни объекта: Как создаются и удаляются объекты](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 Ключевое слово `New` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.OutOfMemoryException>
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Время существования: Способ создания и уничтожения объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
