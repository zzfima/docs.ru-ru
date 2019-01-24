---
title: Свойство по умолчанию &#39; &lt;propertyname1&gt; &#39; конфликтует со свойством по умолчанию &#39; &lt;имя_свойства2&gt; &#39; в &#39; &lt;classname&gt; &#39;и должен быть объявлен &#39;Shadows&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 3099467fa3c5a162c13c9235fb8d55375953ba3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521430"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="3f175-102">Свойство по умолчанию &#39; &lt;propertyname1&gt; &#39; конфликтует со свойством по умолчанию &#39; &lt;имя_свойства2&gt; &#39; в &#39; &lt;classname&gt; &#39;и должен быть объявлен &#39;Shadows&#39;</span><span class="sxs-lookup"><span data-stu-id="3f175-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="3f175-103">Свойство объявлено с тем же именем, что это свойство, определенное в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="3f175-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="3f175-104">В этом случае свойство в данном классе должно затемнять свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="3f175-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="3f175-105">Это сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="3f175-105">This message is a warning.</span></span> <span data-ttu-id="3f175-106">`Shadows` подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f175-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="3f175-107">Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3f175-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3f175-108">**Идентификатор ошибки:** BC40007</span><span class="sxs-lookup"><span data-stu-id="3f175-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f175-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3f175-109">To correct this error</span></span>  
  
-   <span data-ttu-id="3f175-110">Добавление `Shadows` объявляемого ключевое слово объявления, или измените имя свойства.</span><span class="sxs-lookup"><span data-stu-id="3f175-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f175-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3f175-111">See also</span></span>
- [<span data-ttu-id="3f175-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="3f175-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="3f175-113">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f175-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
