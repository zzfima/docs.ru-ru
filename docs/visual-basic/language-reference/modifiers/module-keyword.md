---
title: <keyword> модуля
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: cd2f762181b5a702f0b0defd5b71bb7bdf129c7b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351555"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="2cae7-102">Ключевое слово \<модуля > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cae7-102">Module \<keyword> (Visual Basic)</span></span>
<span data-ttu-id="2cae7-103">Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.</span><span class="sxs-lookup"><span data-stu-id="2cae7-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cae7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="2cae7-104">Remarks</span></span>  
 <span data-ttu-id="2cae7-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="2cae7-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="2cae7-106">Вы применяете такой атрибут, присоединяя блок атрибута в угловых скобках (`< >`) непосредственно к оператору объявления.</span><span class="sxs-lookup"><span data-stu-id="2cae7-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="2cae7-107">Если атрибут относится не только к следующему элементу, но и к текущему модулю сборки, блок атрибута помещается в начало исходного файла и определяется атрибутом с ключевым словом `Module`.</span><span class="sxs-lookup"><span data-stu-id="2cae7-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="2cae7-108">Если он применяется ко всей сборке, используется ключевое слово [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) .</span><span class="sxs-lookup"><span data-stu-id="2cae7-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="2cae7-109">Модификатор `Module` не совпадает с [оператором Module](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2cae7-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cae7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2cae7-110">See also</span></span>

- [<span data-ttu-id="2cae7-111">Сборка</span><span class="sxs-lookup"><span data-stu-id="2cae7-111">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)
- [<span data-ttu-id="2cae7-112">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="2cae7-112">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="2cae7-113">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="2cae7-113">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
