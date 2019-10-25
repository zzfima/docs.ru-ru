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
ms.openlocfilehash: c0870f4b056658a22928769c369024cdda24f354
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799034"
---
# <a name="new-operator-visual-basic"></a>Оператор New (Visual Basic)

Вводит предложение `New` для создания нового экземпляра объекта, задает ограничение конструктора для параметра типа или определяет `Sub`ую процедуру как конструктор класса.

## <a name="remarks"></a>Заметки

В объявлении или операторе присваивания в предложении `New` необходимо указать определенный класс, из которого можно создать экземпляр. Это означает, что класс должен предоставлять один или несколько конструкторов, к которым вызывающий код может получить доступ.

Предложение `New` можно использовать в операторе объявления или в операторе присваивания. При выполнении инструкции вызывается соответствующий конструктор указанного класса, передавая все предоставленные аргументы. В следующем примере демонстрируется создание экземпляров класса `Customer`, который имеет два конструктора, один из которых не принимает параметры и один принимает строковый параметр:

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

Поскольку массивы являются классами, `New` может создать новый экземпляр массива, как показано в следующем примере:

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

Среда CLR вызывает ошибку <xref:System.OutOfMemoryException>, если недостаточно памяти для создания нового экземпляра.

> [!NOTE]
> Ключевое слово `New` также используется в списках параметров типов, чтобы указать, что предоставленный тип должен предоставлять доступный конструктор без параметров. Дополнительные сведения о параметрах типа и ограничениях см. в разделе [Type List](../statements/type-list.md).

Чтобы создать процедуру конструктора для класса, задайте в качестве имени `Sub` процедуры ключевое слово `New`. Дополнительные сведения см. в разделе [время существования объекта: как создаются и уничтожаются объекты](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

Ключевое слово `New` можно использовать в следующих контекстах:

- [Оператор Dim](../statements/dim-statement.md)
- [Of](../statements/of-clause.md)
- [Оператор Sub](../statements/sub-statement.md)

## <a name="see-also"></a>См. также

- <xref:System.OutOfMemoryException>
- [Ключевые слова](../keywords/index.md)
- [Список типов](../statements/type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Время существования. Создание и уничтожение объектов](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
