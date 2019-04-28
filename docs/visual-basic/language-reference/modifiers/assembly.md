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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801998"
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
