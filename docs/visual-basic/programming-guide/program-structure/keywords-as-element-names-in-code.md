---
title: Ключевые слова как имена элементов в коде (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Ключевые слова как имена элементов в коде (Visual Basic)
Любой элемент программы, такие как переменная, класс или член, может иметь имя, совпадающее с именем служебное слово. Например, можно создать переменную с именем `Loop`. Тем не менее для обращения к вашей версии, который имеет то же имя, как и служебное `Loop` ключевое слово — необходимо добавить перед ее именем полное имя пространства имен или заключите его в квадратные скобки (`[ ]`), как показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Если этого не сделать, либо из указанных, то Visual Basic предполагает использование встроенного `Loop` ключевое слово и приводит к ошибке, как показано в следующем примере:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Можно использовать квадратные скобки, при ссылке на формах и элементах управления, а также при объявлении переменной или определении процедуры с тем же именем, как служебное слово. Его можно легко забыть квалифицировать имена или содержать квадратные скобки и таким образом приведет к ошибкам в коде и затруднять чтение. По этой причине рекомендуется не использовать служебные ключевые слова как имена элементов программы. Тем не менее если будущей версии Visual Basic определяет новое ключевое слово конфликтует с существующим именем формы или элемента управления, то вы может использовать этот метод при обновлении кода для работы с новой версией.  
  
> [!NOTE]
>  Программа также могут содержаться имена элементов, предоставляемых других сборок. Если эти имена конфликтуют с ограниченными ключевыми словами, квадратные скобки вокруг них вызывает Visual Basic, чтобы интерпретировать их как определенные вами элементы.  
  
## <a name="see-also"></a>См. также  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
