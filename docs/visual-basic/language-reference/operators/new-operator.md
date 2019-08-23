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
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955882"
---
# <a name="new-operator-visual-basic"></a>Оператор New (Visual Basic)
Вводит предложение для создания нового экземпляра объекта, задает ограничение конструктора для параметра типа или `Sub` определяет процедуру как конструктор класса. `New`  
  
## <a name="remarks"></a>Примечания  
 В объявлении или операторе `New` присваивания в предложении необходимо указать определенный класс, из которого можно создать экземпляр. Это означает, что класс должен предоставлять один или несколько конструкторов, к которым вызывающий код может получить доступ.  
  
 `New` Предложение можно использовать в операторе объявления или в операторе присваивания. При выполнении инструкции вызывается соответствующий конструктор указанного класса, передавая все предоставленные аргументы. В следующем примере демонстрируется создание экземпляров `Customer` класса, который имеет два конструктора, один из которых не принимает параметры и один принимает строковый параметр.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Поскольку массивы являются классами, `New` может создать новый экземпляр массива, как показано в следующих примерах.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Среда CLR выдает <xref:System.OutOfMemoryException> ошибку, если недостаточно памяти для создания нового экземпляра.  
  
> [!NOTE]
> `New` Ключевое слово также используется в списках параметров типов, чтобы указать, что предоставленный тип должен предоставлять доступный конструктор без параметров. Дополнительные сведения о параметрах типа и ограничениях см. в разделе [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Чтобы создать процедуру конструктора для класса, задайте в качестве имени `Sub` процедуры `New` ключевое слово. Дополнительные сведения см. в [разделе время существования объекта: Как создаются и уничтожаются](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)объекты.  
  
 Ключевое слово `New` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.OutOfMemoryException>
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Время существования объекта: Как создаются и уничтожаются объекты](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
