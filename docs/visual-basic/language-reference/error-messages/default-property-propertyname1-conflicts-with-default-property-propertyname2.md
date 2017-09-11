---
title: "По умолчанию свойство &quot;&lt;propertyname1&gt;«конфликтует со свойством по умолчанию»&lt;propertyname2&gt;«in»&lt;classname&gt;&quot; и должен быть объявлен как &quot;Shadows&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
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
ms.openlocfilehash: 6eac9e0fdc468e27afac82a8a7c9b2251a8f7317
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="2a79d-102">По умолчанию свойство "&lt;propertyname1&gt;«конфликтует со свойством по умолчанию»&lt;propertyname2&gt;«in»&lt;classname&gt;" и должен быть объявлен как 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="2a79d-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="2a79d-103">Свойство объявлено с тем же именем, как свойства, определенные в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="2a79d-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="2a79d-104">В этом случае свойство в данном классе должно скрывать свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="2a79d-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="2a79d-105">Это сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="2a79d-105">This message is a warning.</span></span> <span data-ttu-id="2a79d-106">`Shadows`подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a79d-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="2a79d-107">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2a79d-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2a79d-108">**Идентификатор ошибки:** BC40007</span><span class="sxs-lookup"><span data-stu-id="2a79d-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2a79d-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2a79d-109">To correct this error</span></span>  
  
-   <span data-ttu-id="2a79d-110">Добавление `Shadows` объявляемого ключевое слово объявление или измените имя свойства.</span><span class="sxs-lookup"><span data-stu-id="2a79d-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a79d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2a79d-111">See Also</span></span>  
 <span data-ttu-id="2a79d-112">[Тени](../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="2a79d-112">[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="2a79d-113"> [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span><span class="sxs-lookup"><span data-stu-id="2a79d-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span></span>
