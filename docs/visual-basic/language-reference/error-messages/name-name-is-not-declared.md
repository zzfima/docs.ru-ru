---
title: "Имя &quot;&lt;имя&gt;&quot; не объявлен | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
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
ms.openlocfilehash: 1396f24a34a37db064e73d7e259c04050f409ad2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="7868e-102">Имя "&lt;имя&gt;" не объявлен как</span><span class="sxs-lookup"><span data-stu-id="7868e-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="7868e-103">Оператор ссылается на элемент программирования, но компилятор не может найти элемент с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="7868e-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="7868e-104">**Идентификатор ошибки:** BC30451</span><span class="sxs-lookup"><span data-stu-id="7868e-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7868e-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7868e-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="7868e-106">Проверьте правильность написания в ссылающемся операторе.</span><span class="sxs-lookup"><span data-stu-id="7868e-106">Check the spelling of the name in the referring statement.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7868e-107">не учитывает регистр, но любое другое изменение в орфографии рассматривается как полностью другое имя.</span><span class="sxs-lookup"><span data-stu-id="7868e-107"> is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="7868e-108">Обратите внимание, что символ подчеркивания (`_`) является частью имени и, следовательно, частью орфографии.</span><span class="sxs-lookup"><span data-stu-id="7868e-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="7868e-109">Убедитесь, что оператор доступа к членам (`.`) между объектом и его членах.</span><span class="sxs-lookup"><span data-stu-id="7868e-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="7868e-110">Например, если у вас есть <xref:System.Windows.Forms.TextBox>элемент управления с именем `TextBox1`, чтобы получить доступ к его <xref:System.Windows.Forms.TextBoxBase.Text%2A>свойство, следует ввести `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="7868e-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="7868e-111">Если вместо этого ввести `TextBox1Text`, будет создано другое имя.</span><span class="sxs-lookup"><span data-stu-id="7868e-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="7868e-112">Если правильность написания и синтаксис любой доступ к членам объекта, убедитесь, что элемент был объявлен.</span><span class="sxs-lookup"><span data-stu-id="7868e-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="7868e-113">Дополнительные сведения см. в разделе [объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="7868e-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="7868e-114">Если элемент программирования был объявлен, проверьте его в области видимости.</span><span class="sxs-lookup"><span data-stu-id="7868e-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="7868e-115">Если ссылающийся оператор находится вне области объявления программного элемента, может потребоваться уточнение имени элемента.</span><span class="sxs-lookup"><span data-stu-id="7868e-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="7868e-116">Дополнительные сведения см. в разделе [область в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="7868e-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7868e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7868e-117">See Also</span></span>  
 <span data-ttu-id="7868e-118">[Сводка объявлений и констант](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span><span class="sxs-lookup"><span data-stu-id="7868e-118">[Declarations and Constants Summary](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span></span>  
<span data-ttu-id="7868e-119"> [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="7868e-119"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="7868e-120"> [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="7868e-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="7868e-121"> [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="7868e-121"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
