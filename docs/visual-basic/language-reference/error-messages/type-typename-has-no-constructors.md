---
title: "Тип &quot;&lt;typename&gt;&quot; не имеет конструкторов | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30251
- vbc30251
dev_langs:
- VB
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 505e3bbdfa830394efcea7226897ec0d3e6d2b02
ms.lasthandoff: 03/13/2017

---
# <a name="type-39lttypenamegt39-has-no-constructors"></a>Тип "&lt;typename&gt;" не имеет конструкторов
Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.  
  
 **Идентификатор ошибки:** BC30251  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.  
  
2.  Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.  
  
3.  Если устранить ошибку не удается, переустановите компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
4.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Обращайтесь к нам](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
