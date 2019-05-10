---
title: Свойство <propertyname1>, используемое по умолчанию, конфликтует со свойством <propertyname2>, используемым по умолчанию в классе <classname>, и должно быть объявлено с ключевым словом Shadows
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: c964003217e7b96cf25288e2ae6ae6a2fb07a6c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651381"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="9bc84-102">Свойство по умолчанию "\<propertyname1 >" конфликтует со свойством по умолчанию "\<имя_свойства2 >" в "\<имя_класса >" и должен быть объявлен «Shadows»</span><span class="sxs-lookup"><span data-stu-id="9bc84-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="9bc84-103">Свойство объявлено с тем же именем, что это свойство, определенное в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="9bc84-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="9bc84-104">В этом случае свойство в данном классе должно затемнять свойство базового класса.</span><span class="sxs-lookup"><span data-stu-id="9bc84-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="9bc84-105">Это сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="9bc84-105">This message is a warning.</span></span> <span data-ttu-id="9bc84-106">`Shadows` подразумевается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9bc84-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="9bc84-107">Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9bc84-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9bc84-108">**Идентификатор ошибки:** BC40007</span><span class="sxs-lookup"><span data-stu-id="9bc84-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9bc84-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9bc84-109">To correct this error</span></span>  
  
- <span data-ttu-id="9bc84-110">Добавление `Shadows` объявляемого ключевое слово объявления, или измените имя свойства.</span><span class="sxs-lookup"><span data-stu-id="9bc84-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc84-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9bc84-111">See also</span></span>

- [<span data-ttu-id="9bc84-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="9bc84-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="9bc84-113">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9bc84-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
