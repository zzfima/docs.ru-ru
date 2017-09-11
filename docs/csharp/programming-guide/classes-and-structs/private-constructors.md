---
title: "Закрытые конструкторы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
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
ms.openlocfilehash: 1ccd3db5f95e3a237bb37d9e09c34f415fcfd752
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="54cdd-102">Закрытые конструкторы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="54cdd-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="54cdd-103">Закрытый конструктор — это особый конструктор экземпляров.</span><span class="sxs-lookup"><span data-stu-id="54cdd-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="54cdd-104">Обычно он используется в классах, содержащих только статические элементы.</span><span class="sxs-lookup"><span data-stu-id="54cdd-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="54cdd-105">Если в классе один или несколько закрытых конструкторов и ни одного открытого конструктора, то прочие классы (за исключением вложенных классов) не смогут создавать экземпляры этого класса.</span><span class="sxs-lookup"><span data-stu-id="54cdd-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="54cdd-106">Например:</span><span class="sxs-lookup"><span data-stu-id="54cdd-106">For example:</span></span>  
  
 <span data-ttu-id="54cdd-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="54cdd-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="54cdd-108">Объявление пустого конструктора запрещает автоматическое создание конструктора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54cdd-108">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="54cdd-109">Обратите внимание, что если не использовать с конструктором модификатор доступа, то по умолчанию он все равно будет закрытым.</span><span class="sxs-lookup"><span data-stu-id="54cdd-109">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="54cdd-110">Однако обычно используется модификатор [private](../../../csharp/language-reference/keywords/private.md), чтобы явно обозначить невозможность создания экземпляров этого класса.</span><span class="sxs-lookup"><span data-stu-id="54cdd-110">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="54cdd-111">Закрытые конструкторы используются, чтобы не допустить создания экземпляров класса при отсутствии полей или методов экземпляра, например для класса <xref:System.Math>, или когда осуществляется вызов метода для получения экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="54cdd-111">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="54cdd-112">Если все методы в классе являются статическими, имеет смысл сделать статическим весь класс.</span><span class="sxs-lookup"><span data-stu-id="54cdd-112">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="54cdd-113">Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="54cdd-113">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54cdd-114">Пример</span><span class="sxs-lookup"><span data-stu-id="54cdd-114">Example</span></span>  
 <span data-ttu-id="54cdd-115">Ниже приведен пример класса с закрытым конструктором.</span><span class="sxs-lookup"><span data-stu-id="54cdd-115">The following is an example of a class using a private constructor.</span></span>  
  
 <span data-ttu-id="54cdd-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="54cdd-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="54cdd-117">Обратите внимание, что если в примере раскомментировать следующий оператор, возникнет ошибка, так как конструктор недоступен из-за уровня защиты:</span><span class="sxs-lookup"><span data-stu-id="54cdd-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 <span data-ttu-id="54cdd-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="54cdd-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="54cdd-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="54cdd-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="54cdd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="54cdd-120">See Also</span></span>  
 <span data-ttu-id="54cdd-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="54cdd-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="54cdd-122">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="54cdd-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="54cdd-123">[Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="54cdd-123">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="54cdd-124">[Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="54cdd-124">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="54cdd-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="54cdd-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="54cdd-126">public</span><span class="sxs-lookup"><span data-stu-id="54cdd-126">public</span></span>](../../../csharp/language-reference/keywords/public.md)

