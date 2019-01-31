---
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af3bc95e2db88577c7c53e4b58fb60aed8a83453
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267656"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>"\<ключевое слово >" является допустимым только в методе экземпляра
`Me`, `MyClass`, И `MyBase` ключевые слова ссылаются на экземпляры определенного класса. Их нельзя использовать внутри совместно используемого `Function` или `Sub` процедуры.  
  
 **Идентификатор ошибки:** BC30043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.  
  
## <a name="see-also"></a>См. также
- [Присваивание объектных переменных](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
