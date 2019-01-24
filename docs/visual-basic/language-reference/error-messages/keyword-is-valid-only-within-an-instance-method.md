---
title: '&#39;&lt;Ключевое слово&gt; &#39; является допустимым только в методе экземпляра'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: a464a059aa2d13e3472b9770960384b6be398092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595946"
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a>&#39;&lt;Ключевое слово&gt; &#39; является допустимым только в методе экземпляра
`Me`, `MyClass`, И `MyBase` ключевые слова ссылаются на экземпляры определенного класса. Их нельзя использовать внутри совместно используемого `Function` или `Sub` процедуры.  
  
 **Идентификатор ошибки:** BC30043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.  
  
## <a name="see-also"></a>См. также
- [Присваивание объектных переменных](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
