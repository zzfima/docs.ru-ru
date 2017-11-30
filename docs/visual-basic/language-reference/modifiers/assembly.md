---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef4434f0bc520abfc621567fc68e0b8bcfd6e381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="4eb88-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4eb88-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="4eb88-103">Указывает, что атрибут в начале исходного файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="4eb88-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4eb88-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="4eb88-104">Remarks</span></span>  
 <span data-ttu-id="4eb88-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="4eb88-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="4eb88-106">Применяйте такой атрибут путем присоединения блока атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="4eb88-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="4eb88-107">Если атрибут принадлежит не только к следующему элементу, но ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="4eb88-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="4eb88-108">Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="4eb88-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="4eb88-109">Можно также применить атрибут к сборке в файле AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="4eb88-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb88-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4eb88-110">See Also</span></span>  
 [<span data-ttu-id="4eb88-111">Module \<ключевое_слово></span><span class="sxs-lookup"><span data-stu-id="4eb88-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="4eb88-112">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="4eb88-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

