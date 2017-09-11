---
title: "разделяемый (тип) (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5405455d933f6512cfa3a18e1a545556c5715151
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="partial-type-c-reference"></a><span data-ttu-id="856c5-102">разделяемый (тип) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="856c5-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="856c5-103">Определения разделяемых типов позволяют разделять определения классов, структур и интерфейсов на несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="856c5-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="856c5-104">В File1.cs:</span><span class="sxs-lookup"><span data-stu-id="856c5-104">In File1.cs:</span></span>  
  
 <span data-ttu-id="856c5-105">[!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="856c5-105">[!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]</span></span>  
  
 <span data-ttu-id="856c5-106">В File2.cs объявление:</span><span class="sxs-lookup"><span data-stu-id="856c5-106">In File2.cs the declaration:</span></span>  
  
 <span data-ttu-id="856c5-107">[!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="856c5-107">[!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="856c5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="856c5-108">Remarks</span></span>  
 <span data-ttu-id="856c5-109">Разделение типа класса, структуры или интерфейса на несколько файлов может пригодиться при работе с крупными проектами или с автоматически созданным кодом, например предоставляемым [конструктором Windows Forms](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15).</span><span class="sxs-lookup"><span data-stu-id="856c5-109">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15).</span></span> <span data-ttu-id="856c5-110">Разделяемый тип может содержать [разделяемый метод](../../../csharp/language-reference/keywords/partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="856c5-110">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="856c5-111">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="856c5-111">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="856c5-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="856c5-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="856c5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="856c5-113">See Also</span></span>  
 <span data-ttu-id="856c5-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="856c5-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="856c5-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="856c5-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="856c5-116">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="856c5-116">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="856c5-117">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="856c5-117">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)

