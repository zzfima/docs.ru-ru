---
title: "Оператор New (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74f0352379e861ad135ea23d31ea07d638f9e6c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-visual-basic"></a>Оператор New (Visual Basic)
Представляет `New` предложений, чтобы создать новый экземпляр объекта, задает ограничение конструктору по параметру типа, либо определяет `Sub` процедуры как конструктор класса.  
  
## <a name="remarks"></a>Примечания  
 В объявлении или оператор присваивания `New` предложения необходимо указать определенный класс, из которого может быть создан экземпляр. Это означает, что класс должен предоставлять один или несколько конструкторов, которые вызывающий код может получить доступ.  
  
 Можно использовать `New` предложение в операторе объявления или присваивания. При выполнении оператора вызывается соответствующий конструктор указанного класса, передавая все аргументы, которые вы задали. В следующем примере демонстрируется это путем создания экземпляров `Customer` класс, который имеет два конструктора, один, который не имеет параметров, а другой принимает строковый параметр.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Поскольку массивы являются классами, `New` можно создать новый экземпляр массива, как показано в следующих примерах.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Общеязыковая среда выполнения (CLR) создает <xref:System.OutOfMemoryException> ошибки, если недостаточно памяти для создания нового экземпляра.  
  
> [!NOTE]
>  `New` Ключевое слово также используется в списках параметров типа для указания, что данный тип должен предоставлять доступ к конструктору без параметров. Дополнительные сведения о параметрах типа и ограничениях см. в разделе [список типов](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово. Дополнительные сведения см. в разделе [время существования объекта: как объекты, создание и удаление](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 Ключевое слово `New` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 <xref:System.OutOfMemoryException>  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Время существования. Создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
