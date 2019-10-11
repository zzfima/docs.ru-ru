---
title: <proceduresignature1> не соответствует CLS, поскольку он перегружает <proceduresignature2>, который отличается от него только массивом типов параметров или рангом типов параметра массива
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250172"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="80598-102">\<proceduresignature1 > несовместим с CLS, так как он перегружает \<proceduresignature2 >, который отличается от него только массивом типов параметров массива или рангом типов параметров массива.</span><span class="sxs-lookup"><span data-stu-id="80598-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="80598-103">Процедура или свойство помечается как `<CLSCompliant(True)>` при переопределении другой процедуры или свойства, а единственное различие между их списками параметров — уровень вложенности массива массивов или ранг массива.</span><span class="sxs-lookup"><span data-stu-id="80598-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>
  
 <span data-ttu-id="80598-104">В следующих объявлениях второе и третье объявления создают эту ошибку:</span><span class="sxs-lookup"><span data-stu-id="80598-104">In the following declarations, the second and third declarations generate this error:</span></span>
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 <span data-ttu-id="80598-105">Второе объявление изменяет исходный одномерный параметр `arrayParam` на массив массивов.</span><span class="sxs-lookup"><span data-stu-id="80598-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="80598-106">Третье объявление изменяет `arrayParam` на двухмерный массив (ранг 2).</span><span class="sxs-lookup"><span data-stu-id="80598-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="80598-107">Хотя Visual Basic допускает, чтобы перегрузки отличались только одним из этих изменений, такая перегрузка не соответствует [языковым независимостьм и зависимым от языка компонентам](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="80598-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="80598-108">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="80598-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="80598-109">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="80598-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="80598-110">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="80598-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="80598-111">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="80598-111">By default, this message is a warning.</span></span> <span data-ttu-id="80598-112">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="80598-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="80598-113">**Идентификатор ошибки:** BC40035</span><span class="sxs-lookup"><span data-stu-id="80598-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80598-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="80598-114">To correct this error</span></span>  
  
- <span data-ttu-id="80598-115">Если требуется CLS-совместимость, определите перегрузки так, чтобы они отличались друг от друга более разными способами, чем изменения, упомянутые на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="80598-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="80598-116">Если требуется, чтобы перегрузки отличались только изменениями, упоминаемыми на этой странице справки, удалите <xref:System.CLSCompliantAttribute> из определений или пометьте их как `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="80598-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80598-117">См. также</span><span class="sxs-lookup"><span data-stu-id="80598-117">See also</span></span>

- [<span data-ttu-id="80598-118">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="80598-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="80598-119">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="80598-119">Overloads</span></span>](../modifiers/overloads.md)
