---
title: Свойство по умолчанию &#39; &lt;свойство имя_свойства1&gt;&#39; противоречит свойству по умолчанию &#39;&lt; имя_свойства2&gt;&#39; в &#39;&lt; className&gt;&#39; и поэтому должен быть объявлен как &#39; Shadows &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="e1707-102">Свойство по умолчанию &#39; &lt;свойство имя_свойства1&gt;&#39; противоречит свойству по умолчанию &#39;&lt; имя_свойства2&gt;&#39; в &#39;&lt; className&gt;&#39; и поэтому должен быть объявлен как &#39; Shadows &#39;</span><span class="sxs-lookup"><span data-stu-id="e1707-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="e1707-103">Свойство объявлено с тем же именем, как свойство, определенное в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="e1707-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="e1707-104">В этом случае свойство в данном классе должно скрывать свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="e1707-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="e1707-105">Это сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="e1707-105">This message is a warning.</span></span> <span data-ttu-id="e1707-106">`Shadows` подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1707-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="e1707-107">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e1707-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e1707-108">**Идентификатор ошибки:** BC40007</span><span class="sxs-lookup"><span data-stu-id="e1707-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e1707-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e1707-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e1707-110">Добавить `Shadows` объявляемого ключевое слово объявления или измените имя свойства.</span><span class="sxs-lookup"><span data-stu-id="e1707-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1707-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e1707-111">See Also</span></span>  
 [<span data-ttu-id="e1707-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="e1707-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="e1707-113">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1707-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
