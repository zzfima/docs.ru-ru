---
title: Имя &#39; &lt;имя&gt; &#39; не объявлена
ms.date: 07/20/2015
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: e17017e84720a2581abc5115338352aacc02d473
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="f3dbc-102">Имя &#39; &lt;имя&gt; &#39; не объявлена</span><span class="sxs-lookup"><span data-stu-id="f3dbc-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="f3dbc-103">Оператор ссылается на элемент программирования, но компилятор не может найти элемент с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="f3dbc-104">**Идентификатор ошибки:** BC30451</span><span class="sxs-lookup"><span data-stu-id="f3dbc-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f3dbc-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f3dbc-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f3dbc-106">Проверьте правильность написания в ссылающемся операторе.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="f3dbc-107">Visual Basic не учитывает регистр, но любое другое изменение в орфографии рассматривается как полностью другое имя.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="f3dbc-108">Обратите внимание, что символ подчеркивания (`_`) является частью имени и, следовательно, частью орфографии.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="f3dbc-109">Убедитесь, что оператор доступа к членам (`.`) между объектом и его членах.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="f3dbc-110">Например, если у вас есть элемент управления <xref:System.Windows.Forms.TextBox> с именем `TextBox1`, то для доступа к его свойству <xref:System.Windows.Forms.TextBoxBase.Text%2A> следует ввести `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="f3dbc-111">Если вместо этого ввести `TextBox1Text`, будет создано другое имя.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="f3dbc-112">Если правильность написания и имеет правильный синтаксис любой доступ к членам объекта, убедитесь, что был объявлен элемент.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="f3dbc-113">Дополнительные сведения см. в разделе [объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="f3dbc-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="f3dbc-114">Если программный элемент объявлен, проверьте, что он находится в области.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="f3dbc-115">Если ссылающийся оператор находится вне области объявления программного элемента, может потребоваться уточнение имени элемента.</span><span class="sxs-lookup"><span data-stu-id="f3dbc-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="f3dbc-116">Дополнительные сведения см. в разделе [области в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="f3dbc-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dbc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f3dbc-117">See Also</span></span>  
 [<span data-ttu-id="f3dbc-118">Сводка по объявлениям и константам</span><span class="sxs-lookup"><span data-stu-id="f3dbc-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="f3dbc-119">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3dbc-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="f3dbc-120">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="f3dbc-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="f3dbc-121">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="f3dbc-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
