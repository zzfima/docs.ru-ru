---
title: Ключевые слова как имена элементов в коде (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 2e3613bd4a74da51cf7dbb63e52eddca811ca8e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947663"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Ключевые слова как имена элементов в коде (Visual Basic)
Любой элемент программы (например, переменная, класс или член) может иметь то же имя, что и ключевое слово Restricted. Например, можно создать переменную с именем `Loop`. Однако для ссылки на вашу версию, которая имеет то же имя, что и ключевое слово `Loop` Restricted, необходимо либо указать перед ней полную уточняющую строку, либо заключить ее в квадратные скобки (`[ ]`), как показано в следующем примере.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Если вы не выполняете ни одно из этих действий, Visual Basic предполагает использование встроенного `Loop` ключевого слова и выдает ошибку, как показано в следующем примере:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 При обращении к формам и элементам управления можно использовать квадратные скобки, а также при объявлении переменной или при определении процедуры с тем же именем, что и ключевое слово Restricted. Можно легко забыть определить имена или включить в них квадратные скобки, что приводит к ошибкам в коде и затрудняет чтение. По этой причине не рекомендуется использовать в качестве имен программных элементов ограниченные ключевые слова. Однако если в будущей версии Visual Basic определено новое ключевое слово, которое вступает в противоречие с существующей формой или именем элемента управления, можно использовать этот метод при обновлении кода для работы с новой версией.  
  
> [!NOTE]
> Программа также может включать имена элементов, предоставляемых другими ссылочными сборками. Если эти имена конфликтуют с ограниченными ключевыми словами, то при заключении в квадратные скобки они приводят к тому, что Visual Basic интерпретирует их как определенные элементы.  
  
## <a name="see-also"></a>См. также

- [Соглашения об именовании Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
