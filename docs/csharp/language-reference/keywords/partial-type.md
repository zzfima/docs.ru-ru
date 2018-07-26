---
title: разделяемый (тип) (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4f57149dd18deb08aa11b72d0a6d5f71b3838bd1
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960301"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="ff596-102">разделяемый (тип) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ff596-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="ff596-103">Определения разделяемых типов позволяют разделять определения классов, структур и интерфейсов на несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="ff596-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="ff596-104">В File1.cs:</span><span class="sxs-lookup"><span data-stu-id="ff596-104">In File1.cs:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 <span data-ttu-id="ff596-105">В File2.cs объявление:</span><span class="sxs-lookup"><span data-stu-id="ff596-105">In File2.cs the declaration:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="ff596-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff596-106">Remarks</span></span>  
 <span data-ttu-id="ff596-107">Разделение типа класса, структуры или интерфейса на несколько файлов может пригодиться при работе с крупными проектами или с автоматически созданным кодом, например предоставляемым [конструктором Windows Forms](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ff596-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="ff596-108">Разделяемый тип может содержать [разделяемый метод](../../../csharp/language-reference/keywords/partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="ff596-108">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="ff596-109">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ff596-109">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ff596-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ff596-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff596-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ff596-111">See Also</span></span>  
 [<span data-ttu-id="ff596-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ff596-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ff596-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff596-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ff596-114">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="ff596-114">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="ff596-115">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="ff596-115">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
