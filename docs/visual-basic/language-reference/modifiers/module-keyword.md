---
title: <keyword> модуля
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: cd2f762181b5a702f0b0defd5b71bb7bdf129c7b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351555"
---
# <a name="module-keyword-visual-basic"></a>Ключевое слово \<модуля > (Visual Basic)
Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.  
  
## <a name="remarks"></a>Примечания  
 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Вы применяете такой атрибут, присоединяя блок атрибута в угловых скобках (`< >`) непосредственно к оператору объявления.  
  
 Если атрибут относится не только к следующему элементу, но и к текущему модулю сборки, блок атрибута помещается в начало исходного файла и определяется атрибутом с ключевым словом `Module`. Если он применяется ко всей сборке, используется ключевое слово [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) .  
  
 Модификатор `Module` не совпадает с [оператором Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
## <a name="see-also"></a>См. также

- [Сборка](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
