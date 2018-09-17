---
title: Закрытые конструкторы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 1338a6efbe03522093899009178b6f31e558d8dd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45647000"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="f741f-102">Закрытые конструкторы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f741f-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="f741f-103">Закрытый конструктор — это особый конструктор экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f741f-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="f741f-104">Обычно он используется в классах, содержащих только статические элементы.</span><span class="sxs-lookup"><span data-stu-id="f741f-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="f741f-105">Если в классе один или несколько закрытых конструкторов и ни одного открытого конструктора, то прочие классы (за исключением вложенных классов) не смогут создавать экземпляры этого класса.</span><span class="sxs-lookup"><span data-stu-id="f741f-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="f741f-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="f741f-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="f741f-107">Объявление пустого конструктора запрещает автоматическое создание конструктора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f741f-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="f741f-108">Обратите внимание, что если не использовать с конструктором модификатор доступа, то по умолчанию он все равно будет закрытым.</span><span class="sxs-lookup"><span data-stu-id="f741f-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="f741f-109">Однако обычно используется модификатор [private](../../../csharp/language-reference/keywords/private.md), чтобы явно обозначить невозможность создания экземпляров этого класса.</span><span class="sxs-lookup"><span data-stu-id="f741f-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="f741f-110">Закрытые конструкторы используются, чтобы не допустить создания экземпляров класса при отсутствии полей или методов экземпляра, например для класса <xref:System.Math>, или когда осуществляется вызов метода для получения экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="f741f-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="f741f-111">Если все методы в классе являются статическими, имеет смысл сделать статическим весь класс.</span><span class="sxs-lookup"><span data-stu-id="f741f-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="f741f-112">Дополнительные сведения см. в разделе [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="f741f-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f741f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f741f-113">Example</span></span>  
 <span data-ttu-id="f741f-114">Ниже приведен пример класса с закрытым конструктором.</span><span class="sxs-lookup"><span data-stu-id="f741f-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="f741f-115">Обратите внимание, что если в примере раскомментировать следующий оператор, возникнет ошибка, так как конструктор недоступен из-за уровня защиты:</span><span class="sxs-lookup"><span data-stu-id="f741f-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f741f-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f741f-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f741f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f741f-117">See Also</span></span>

- [<span data-ttu-id="f741f-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f741f-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f741f-119">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="f741f-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="f741f-120">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="f741f-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="f741f-121">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="f741f-121">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="f741f-122">private</span><span class="sxs-lookup"><span data-stu-id="f741f-122">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="f741f-123">public</span><span class="sxs-lookup"><span data-stu-id="f741f-123">public</span></span>](../../../csharp/language-reference/keywords/public.md)
