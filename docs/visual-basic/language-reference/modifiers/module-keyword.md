---
title: Модуль &lt;ключевое слово&gt; (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: b412655695c49d1e12a02e005fccfd37d2956787
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595281"
---
# <a name="module-ltkeywordgt-visual-basic"></a><span data-ttu-id="b19a2-102">Модуль &lt;ключевое слово&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b19a2-102">Module &lt;keyword&gt; (Visual Basic)</span></span>
<span data-ttu-id="b19a2-103">Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.</span><span class="sxs-lookup"><span data-stu-id="b19a2-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b19a2-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b19a2-104">Remarks</span></span>  
 <span data-ttu-id="b19a2-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="b19a2-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="b19a2-106">Применяйте такой атрибут путем присоединения блока атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="b19a2-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="b19a2-107">Если атрибут принадлежит не только к следующему элементу, но к текущему модулю сборки, поместите блок атрибута в начале исходного файла и определите атрибут с `Module` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b19a2-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="b19a2-108">Если он применяется ко всей сборке, используйте [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b19a2-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="b19a2-109">`Module` Модификатор не совпадает с [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b19a2-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19a2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b19a2-110">See Also</span></span>  
 [<span data-ttu-id="b19a2-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="b19a2-111">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="b19a2-112">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="b19a2-112">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="b19a2-113">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="b19a2-113">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

