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
# <a name="assembly-visual-basic"></a><span data-ttu-id="cb283-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb283-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="cb283-103">Указывает, что атрибут в начале исходного файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="cb283-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb283-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb283-104">Remarks</span></span>  
 <span data-ttu-id="cb283-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="cb283-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="cb283-106">Вы применяете такой атрибут, присоединяя блок атрибута в угловых скобках (`< >`) непосредственно к оператору объявления.</span><span class="sxs-lookup"><span data-stu-id="cb283-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="cb283-107">Если атрибут относится не только к следующему элементу, но и ко всей сборке, блок атрибута помещается в начало исходного файла и определяется атрибутом с ключевым словом `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="cb283-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="cb283-108">Если он применяется к текущему модулю сборки, используется ключевое слово [module](../../../visual-basic/language-reference/modifiers/module-keyword.md) .</span><span class="sxs-lookup"><span data-stu-id="cb283-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="cb283-109">Можно также применить атрибут к сборке в файле AssemblyInfo. vb. в этом случае не нужно использовать блок атрибутов в основном файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="cb283-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb283-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cb283-110">See also</span></span>

- [<span data-ttu-id="cb283-111">Module \<ключевое_слово></span><span class="sxs-lookup"><span data-stu-id="cb283-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="cb283-112">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="cb283-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
