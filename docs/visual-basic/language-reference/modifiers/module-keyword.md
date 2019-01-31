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
ms.openlocfilehash: fa798e8a2c82bdf204edb1812b0020f874b1e978
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257711"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="bc75b-102">Модуль \<ключевое слово > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc75b-102">Module \<keyword> (Visual Basic)</span></span>
<span data-ttu-id="bc75b-103">Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.</span><span class="sxs-lookup"><span data-stu-id="bc75b-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc75b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc75b-104">Remarks</span></span>  
 <span data-ttu-id="bc75b-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="bc75b-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="bc75b-106">Применить такой атрибут, подключив блок атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="bc75b-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="bc75b-107">Если атрибут относится не только к следующему элементу, но к текущему модулю сборки, поместите блок атрибута в начале исходного файла и определите атрибут с `Module` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="bc75b-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="bc75b-108">Если он применяется ко всей сборке, использовании [сборки](../../../visual-basic/language-reference/modifiers/assembly.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="bc75b-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="bc75b-109">`Module` Модификатор не так же, как [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bc75b-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc75b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bc75b-110">See also</span></span>
- [<span data-ttu-id="bc75b-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="bc75b-111">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)
- [<span data-ttu-id="bc75b-112">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="bc75b-112">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="bc75b-113">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="bc75b-113">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

