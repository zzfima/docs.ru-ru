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
ms.openlocfilehash: 7ee6cddefd5955ee76510ffeb23335f05460657b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595294"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="0c3eb-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c3eb-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="0c3eb-103">Указывает, что атрибут в начале исходного файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="0c3eb-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c3eb-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c3eb-104">Remarks</span></span>  
 <span data-ttu-id="0c3eb-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="0c3eb-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="0c3eb-106">Применяйте такой атрибут путем присоединения блока атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="0c3eb-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="0c3eb-107">Если атрибут принадлежит не только к следующему элементу, но ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0c3eb-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="0c3eb-108">Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0c3eb-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="0c3eb-109">Можно также применить атрибут к сборке в файле AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="0c3eb-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3eb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0c3eb-110">See Also</span></span>  
 [<span data-ttu-id="0c3eb-111">Module \<ключевое_слово></span><span class="sxs-lookup"><span data-stu-id="0c3eb-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="0c3eb-112">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="0c3eb-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

