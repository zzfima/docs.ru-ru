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
ms.openlocfilehash: e6cb7e7a2520d6bb586dab4ed0af75abb04fabd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726472"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Указывает, что атрибут в начале исходного файла применяется ко всей сборке.  
  
## <a name="remarks"></a>Примечания  
 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Применить такой атрибут, подключив блок атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.  
  
 Если атрибут относится не только к следующему элементу, но ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово. Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.  
  
 Также можно применить атрибут к сборке в файл AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.  
  
## <a name="see-also"></a>См. также
- [Module \<ключевое_слово>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)

