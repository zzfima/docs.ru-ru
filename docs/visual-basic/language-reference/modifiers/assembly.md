---
title: "Сборки (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b496b96360ff891554ab71ba2b3227b2dabbc416
ms.lasthandoff: 03/13/2017

---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Указывает, что атрибут в начале файла применяется ко всей сборке.  
  
## <a name="remarks"></a>Примечания  
 Многие атрибуты относятся к отдельному элементу, такие как класс или свойство. Применяйте такой атрибут путем присоединения блока атрибута в угловых скобках (`< >`), непосредственно в операторе объявления.  
  
 Если атрибут принадлежит не только к следующему элементу, но и ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово. Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.  
  
 Можно также применить атрибут к сборке в файле AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.  
  
## <a name="see-also"></a>См. также  
 [Модуль \<ключевое слово настроек](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)


