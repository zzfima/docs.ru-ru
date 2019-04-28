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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801998"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="1a176-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a176-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="1a176-103">Указывает, что атрибут в начале исходного файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="1a176-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a176-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a176-104">Remarks</span></span>  
 <span data-ttu-id="1a176-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="1a176-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="1a176-106">Применить такой атрибут, подключив блок атрибутов, заданные в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="1a176-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="1a176-107">Если атрибут относится не только к следующему элементу, но ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="1a176-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="1a176-108">Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="1a176-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="1a176-109">Также можно применить атрибут к сборке в файл AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1a176-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a176-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1a176-110">See also</span></span>

- [<span data-ttu-id="1a176-111">Module \<ключевое_слово></span><span class="sxs-lookup"><span data-stu-id="1a176-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="1a176-112">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="1a176-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
