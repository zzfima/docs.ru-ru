---
title: "&#39; &lt;выражение&gt;&#39; нельзя использовать в качестве ограничения типа"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords: BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c7271018a93c97ed90dc272f7f5404c0f0a22d42
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="a7de8-102">&#39; &lt;выражение&gt;&#39; нельзя использовать в качестве ограничения типа</span><span class="sxs-lookup"><span data-stu-id="a7de8-102">&#39;&lt;expression&gt;&#39; cannot be used as a type constraint</span></span>
<span data-ttu-id="a7de8-103">Список ограничений включает выражение, которое не представляет допустимое ограничение для параметра типа.</span><span class="sxs-lookup"><span data-stu-id="a7de8-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="a7de8-104">Список ограничений назначает требования на тип аргумента, передаваемого параметру типа.</span><span class="sxs-lookup"><span data-stu-id="a7de8-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="a7de8-105">Вы можете указать приведенные ниже требования в любой комбинации.</span><span class="sxs-lookup"><span data-stu-id="a7de8-105">You can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="a7de8-106">Аргумент типа должен реализовывать один или несколько интерфейсов</span><span class="sxs-lookup"><span data-stu-id="a7de8-106">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="a7de8-107">Аргумент типа должен наследовать не более чем от одного класса</span><span class="sxs-lookup"><span data-stu-id="a7de8-107">The type argument must inherit from at most one class</span></span>  
  
-   <span data-ttu-id="a7de8-108">Аргумент типа должен предоставлять конструктор без параметров, к которому создающий код может получить доступ (включая ограничение `New` ).</span><span class="sxs-lookup"><span data-stu-id="a7de8-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="a7de8-109">Если не включать определенный класс или интерфейс в список ограничений, то можно наложить более общее требование, указав одно из приведенных ниже ограничений.</span><span class="sxs-lookup"><span data-stu-id="a7de8-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
-   <span data-ttu-id="a7de8-110">Аргумент типа должен быть типом значения (включая ограничение `Structure` ).</span><span class="sxs-lookup"><span data-stu-id="a7de8-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
-   <span data-ttu-id="a7de8-111">Аргумент типа должен быть ссылочным типом (включая ограничение `Class` ).</span><span class="sxs-lookup"><span data-stu-id="a7de8-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="a7de8-112">Нельзя указывать оба ограничения, `Structure` и `Class` , для одного и того же параметра типа, а также нельзя указывать какое-либо из них более одного раза.</span><span class="sxs-lookup"><span data-stu-id="a7de8-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="a7de8-113">**Идентификатор ошибки:** BC32061</span><span class="sxs-lookup"><span data-stu-id="a7de8-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7de8-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a7de8-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a7de8-115">Проверьте правильность написания выражения и его элементов.</span><span class="sxs-lookup"><span data-stu-id="a7de8-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
-   <span data-ttu-id="a7de8-116">Если выражение не соответствует требованиям предыдущего списка, удалите его из списка ограничений.</span><span class="sxs-lookup"><span data-stu-id="a7de8-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
-   <span data-ttu-id="a7de8-117">Если выражение ссылается на интерфейс или класс, убедитесь, что у компилятора есть доступ к этому интерфейсу или классу.</span><span class="sxs-lookup"><span data-stu-id="a7de8-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="a7de8-118">Возможно, вам потребуется проверить его имя и добавить ссылку в проект.</span><span class="sxs-lookup"><span data-stu-id="a7de8-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="a7de8-119">Дополнительные сведения см. в разделе «Ссылки на проекты» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a7de8-119">For more information, see "References to Projects" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7de8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a7de8-120">See Also</span></span>  
 [<span data-ttu-id="a7de8-121">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7de8-121">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="a7de8-122">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="a7de8-122">Value Types and Reference Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="a7de8-123">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="a7de8-123">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 
