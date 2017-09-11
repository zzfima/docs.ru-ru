---
title: "Модуль &lt;ключевое слово&gt; (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ModuleAttribute
dev_langs:
- VB
helpviewer_keywords:
- Module keyword
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7554c397fbfd3cd61cf19f760eb4664e2deb589b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="module-ltkeywordgt-visual-basic"></a><span data-ttu-id="0a123-102">Модуль &lt;ключевое слово&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a123-102">Module &lt;keyword&gt; (Visual Basic)</span></span>
<span data-ttu-id="0a123-103">Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.</span><span class="sxs-lookup"><span data-stu-id="0a123-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a123-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a123-104">Remarks</span></span>  
 <span data-ttu-id="0a123-105">Многие атрибуты относятся к отдельному элементу, такие как класс или свойство.</span><span class="sxs-lookup"><span data-stu-id="0a123-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="0a123-106">Применяйте такой атрибут путем присоединения блока атрибута в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="0a123-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="0a123-107">Если атрибут принадлежит не только к следующему элементу, но к текущему модулю сборки, поместите блок атрибута в начале исходного файла и определения атрибута с `Module` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0a123-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="0a123-108">Если он применяется ко всей сборке, используйте [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0a123-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="0a123-109">`Module` Модификатор не совпадает с [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0a123-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a123-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0a123-110">See Also</span></span>  
 <span data-ttu-id="0a123-111">[Сборки](../../../visual-basic/language-reference/modifiers/assembly.md) </span><span class="sxs-lookup"><span data-stu-id="0a123-111">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span></span>  
<span data-ttu-id="0a123-112"> [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0a123-112"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="0a123-113"> [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="0a123-113"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>


