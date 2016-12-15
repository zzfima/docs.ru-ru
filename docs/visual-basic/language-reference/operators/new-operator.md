---
title: "Оператор New (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.new"
  - "vb.NewConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ограничения, New - ключевое слово"
  - "ограничения, универсальные типы в Visual Basic"
  - "универсальные шаблоны [Visual Basic], ограничения"
  - "new - ограничение"
  - "New - ключевое слово"
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор New (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Вводится предложение `New` для создания нового экземпляра объекта, задается ограничение конструктора для типа параметра или процедура `Sub` определяется как конструктор класса.  
  
## Заметки  
 В объявлении или присваивании оператор `New` должен указывать определенный класс, из которого можно создать экземпляр.  Это означает, что класс должен предоставлять один или более конструкторов, к которым вызывающий код может получить доступ.  
  
 Зарезервированное слово `New` можно использовать в операторе объявления или присваивания.  При выполнении оператора вызывается соответствующий конструктор указанного класса и ему передаются заданные аргументы.  Следующий пример иллюстрирует это созданием класса `Customer` с двумя конструкторами, один из которых не принимает параметры, а другой принимает строковый параметр.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Поскольку массивы являются классами, оператор `New` может создать новый экземпляр массива, как показано в следующих примерах.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Если для создания нового экземпляра не хватает памяти, то в среде CLR возникнет ошибка <xref:System.OutOfMemoryException>.  
  
> [!NOTE]
>  Ключевое слово `New` также используется в списках параметров типа, указывая, что данный тип должен предоставлять доступный конструктор без параметров.  Дополнительные сведения о параметрах типа и ограничениях см. в разделе [Список типов](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Чтобы создать процедуру конструктора для класса, задайте в качестве имени процедуры `Sub` ключевое слово `New`.  Дополнительные сведения см. в разделе [Время существования: создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 Ключевое слово `New` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 <xref:System.OutOfMemoryException>   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Время существования: создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)