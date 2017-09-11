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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b83102c24c80b7ee6ec4c0ffc4a446e26b7811cf
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="assembly-visual-basic"></a><span data-ttu-id="d688f-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d688f-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="d688f-103">Указывает, что атрибут в начале файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="d688f-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d688f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="d688f-104">Remarks</span></span>  
 <span data-ttu-id="d688f-105">Многие атрибуты относятся к отдельному элементу, такие как класс или свойство.</span><span class="sxs-lookup"><span data-stu-id="d688f-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="d688f-106">Применяйте такой атрибут путем присоединения блока атрибута в угловых скобках (`< >`), непосредственно в операторе объявления.</span><span class="sxs-lookup"><span data-stu-id="d688f-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="d688f-107">Если атрибут принадлежит не только к следующему элементу, но и ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут с `Assembly` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d688f-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="d688f-108">Если он применяется к текущему модулю сборки, используйте [модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="d688f-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="d688f-109">Можно также применить атрибут к сборке в файле AssemblyInfo.vb, в этом случае не нужно использовать блок атрибутов в файле главного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="d688f-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d688f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d688f-110">See Also</span></span>  
 <span data-ttu-id="d688f-111">[Модуль \<ключевое слово настроек](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="d688f-111">[Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="d688f-112"> [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="d688f-112"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>


