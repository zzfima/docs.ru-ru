---
title: Module <keyword> (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: f6ded1184aedf1702f4b6e5eebb85709cf8e39f4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814280"
---
# <a name="module-keyword-visual-basic"></a>Модуль \<ключевое слово > (Visual Basic)
Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.  
  
## <a name="remarks"></a>Примечания  
 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Применить такой атрибут, подключив блок атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.  
  
 Если атрибут относится не только к следующему элементу, но к текущему модулю сборки, поместите блок атрибута в начале исходного файла и определите атрибут с `Module` ключевое слово. Если он применяется ко всей сборке, использовании [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) ключевое слово.  
  
 `Module` Модификатор не так же, как [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
## <a name="see-also"></a>См. также

- [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
