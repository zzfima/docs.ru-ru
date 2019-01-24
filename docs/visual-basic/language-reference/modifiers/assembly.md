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
# <a name="assembly-visual-basic"></a><span data-ttu-id="dc6e9-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc6e9-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="dc6e9-103">Указывает, что атрибут в начале исходного файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="dc6e9-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc6e9-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc6e9-104">Remarks</span></span>  
 <span data-ttu-id="dc6e9-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="dc6e9-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="dc6e9-106">Применить такой атрибут, подключив блок атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="dc6e9-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="dc6e9-107">Если атрибут относится не только к следующему элементу, но ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="dc6e9-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="dc6e9-108">Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="dc6e9-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="dc6e9-109">Также можно применить атрибут к сборке в файл AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="dc6e9-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6e9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="dc6e9-110">See also</span></span>
- [<span data-ttu-id="dc6e9-111">Module \<ключевое_слово></span><span class="sxs-lookup"><span data-stu-id="dc6e9-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="dc6e9-112">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="dc6e9-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

