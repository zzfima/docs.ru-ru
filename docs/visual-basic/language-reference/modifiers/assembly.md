---
title: Assembly
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
ms.openlocfilehash: 1385919a1205a60104125fff1bdd24f409a091df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351639"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Указывает, что атрибут в начале исходного файла применяется ко всей сборке.  
  
## <a name="remarks"></a>Примечания  
 Многие атрибуты относятся к отдельному программному элементу, например классу или свойству. Вы применяете такой атрибут, присоединяя блок атрибута в угловых скобках (`< >`) непосредственно к оператору объявления.  
  
 Если атрибут относится не только к следующему элементу, но и ко всей сборке, блок атрибута помещается в начало исходного файла и определяется атрибутом с ключевым словом `Assembly`. Если он применяется к текущему модулю сборки, используется ключевое слово [module](../../../visual-basic/language-reference/modifiers/module-keyword.md) .  
  
 Можно также применить атрибут к сборке в файле AssemblyInfo. vb. в этом случае не нужно использовать блок атрибутов в основном файле исходного кода.  
  
## <a name="see-also"></a>См. также

- [Module \<ключевое_слово>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
