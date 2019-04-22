---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836731"
---
# <a name="default-visual-basic"></a><span data-ttu-id="739ae-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="739ae-102">Default (Visual Basic)</span></span>
<span data-ttu-id="739ae-103">Определяет свойство как свойство по умолчанию класса, структуры или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="739ae-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="739ae-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="739ae-104">Remarks</span></span>  
 <span data-ttu-id="739ae-105">Класс, структура или интерфейс можно указать не более одного из его свойств, как *свойство по умолчанию*, если это свойство принимает хотя бы один параметр.</span><span class="sxs-lookup"><span data-stu-id="739ae-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="739ae-106">Если код ссылается на класс или структуру без указания члена, Visual Basic устраняет эту ссылку на свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="739ae-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="739ae-107">Свойства по умолчанию может привести к небольшому сокращению символы исходного кода, но они могут сделать код более трудным для чтения.</span><span class="sxs-lookup"><span data-stu-id="739ae-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="739ae-108">Если вызывающий код не знакомы с класса или структуры, когда он ссылается на имя класса или структуры, он не может быть определенные ли такая ссылка обращается к классу или структуре или свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="739ae-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="739ae-109">Это может привести к ошибкам компилятора или ошибки слабая логики времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="739ae-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="739ae-110">Отчасти можно уменьшить вероятность возникновения ошибки свойства по умолчанию, используя [оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) тип компилятора, проверки для `On`.</span><span class="sxs-lookup"><span data-stu-id="739ae-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="739ae-111">Если вы планируете использовать предварительно определенный класс или структура в коде, необходимо определить, имеет ли он свойство по умолчанию и если да, что ее имя —.</span><span class="sxs-lookup"><span data-stu-id="739ae-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="739ae-112">Из-за эти недостатки можно не определять свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="739ae-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="739ae-113">Для удобства чтения кода следует также учитывать всегда относятся ко всем свойствам явным образом, даже свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="739ae-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="739ae-114">`Default` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="739ae-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="739ae-115">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="739ae-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="739ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="739ae-116">See also</span></span>

- [<span data-ttu-id="739ae-117">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="739ae-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="739ae-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="739ae-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
