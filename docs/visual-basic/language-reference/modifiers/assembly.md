---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7ee6cddefd5955ee76510ffeb23335f05460657b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595294"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Указывает, что атрибут в начале исходного файла применяется ко всей сборке.  
  
## <a name="remarks"></a>Примечания  
 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Применяйте такой атрибут путем присоединения блока атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.  
  
 Если атрибут принадлежит не только к следующему элементу, но ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово. Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.  
  
 Можно также применить атрибут к сборке в файле AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.  
  
## <a name="see-also"></a>См. также  
 [Module \<ключевое_слово>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)

