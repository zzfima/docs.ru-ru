---
title: "&lt;proceduresignature1&gt; не является CLS-совместимым, поскольку он перегружает &lt;proceduresignature2&gt; , отличающуюся только массивом типов параметров или рангом типов параметра массива | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
dev_langs:
- VB
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
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
ms.openlocfilehash: d106f59e3faa317f67ee92ddcec8416eeff745d4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="dd38b-102">&lt;proceduresignature1&gt; не является CLS-совместимым, поскольку он перегружает &lt;proceduresignature2&gt; , отличающуюся только массивом типов параметров или рангом типов параметра массива</span><span class="sxs-lookup"><span data-stu-id="dd38b-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="dd38b-103">Процедура или свойство помечено как `<CLSCompliant(True)>` при оно переопределяет, другую процедуру или свойство, единственное отличие между списками их параметров — вложенный уровень массива массивов или ранг массива.</span><span class="sxs-lookup"><span data-stu-id="dd38b-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="dd38b-104">В следующих объявлениях второе и третье объявления создают эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="dd38b-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="dd38b-105">Второе объявление изменяет исходный одномерный параметр `arrayParam` в массив массивов.</span><span class="sxs-lookup"><span data-stu-id="dd38b-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="dd38b-106">Третье объявление превращает `arrayParam` двухмерный массив (ранг 2).</span><span class="sxs-lookup"><span data-stu-id="dd38b-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="dd38b-107">Поскольку Visual Basic допускает перегрузки, поддерживающие только одно из этих изменений, такая перегрузка не соответствует [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="dd38b-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="dd38b-108">При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="dd38b-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="dd38b-109">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="dd38b-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="dd38b-110">Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="dd38b-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="dd38b-111">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="dd38b-111">By default, this message is a warning.</span></span> <span data-ttu-id="dd38b-112">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dd38b-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dd38b-113">**Идентификатор ошибки:** BC40035</span><span class="sxs-lookup"><span data-stu-id="dd38b-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd38b-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="dd38b-114">To correct this error</span></span>  
  
-   <span data-ttu-id="dd38b-115">Если требуется CLS-совместимость, определите перегрузки отличаются друг от друга, шире, чем представлено на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="dd38b-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="dd38b-116">Если требуется, чтобы перегрузки отличались только по признакам, описанным в этой справке страницы, удалите <xref:System.CLSCompliantAttribute>из их определения или пометьте их как `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="dd38b-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd38b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="dd38b-117">See Also</span></span>  
 <span data-ttu-id="dd38b-118">[\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span><span class="sxs-lookup"><span data-stu-id="dd38b-118">[\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span></span>  
<span data-ttu-id="dd38b-119"> [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="dd38b-119"> [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span></span>  
<span data-ttu-id="dd38b-120"> [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="dd38b-120"> [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
