---
title: "Практическое руководство: использование универсального класса (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- type parameters, defining
- data type arguments, defining
- arguments [Visual Basic], data types
- Of keyword, using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters, type
- types [Visual Basic], generic
- parameters, generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters, data type
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d6f5f941887dfc1f93221be1c184f0dcc2789352
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="2b9d4-102">Практическое руководство. Использование универсального класса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b9d4-102">How to: Use a Generic Class (Visual Basic)</span></span>
<span data-ttu-id="2b9d4-103">Класс, принимающий *параметры типа*, называется *универсальным*.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="2b9d4-104">При использовании универсального класса из него можно создать *сконструированный класс*, указав *аргумент типа* для каждого из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="2b9d4-105">После этого можно объявить переменную типа сконструированного класса, а также создать экземпляр такого класса и присвоить его этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="2b9d4-106">Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="2b9d4-107">В следующей процедуре используется универсальный класс, определенный в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], и создается его экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-107">The following procedure takes a generic class defined in the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="2b9d4-108">Использование класса, который принимает параметр типа</span><span class="sxs-lookup"><span data-stu-id="2b9d4-108">To use a class that takes a type parameter</span></span>  
  
1.  <span data-ttu-id="2b9d4-109">В начале файла исходного кода, включают [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Импорт <xref:System.Collections.Generic?displayProperty=fullName>имен.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2b9d4-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="2b9d4-110">Это позволяет ссылаться на <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>класс без необходимости полного имени, чтобы отличить его от других классов очереди, например <xref:System.Collections.Queue?displayProperty=fullName>.</xref:System.Collections.Queue?displayProperty=fullName> </xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2b9d4-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=fullName>.</span></span>  
  
2.  <span data-ttu-id="2b9d4-111">Создайте объект обычным способом, но добавьте `(Of` `type``)` сразу после имени класса.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-111">Create the object in the normal way, but add `(Of` `type``)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="2b9d4-112">В следующем примере используется тот же класс (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) для создания двух объектов очередей, содержащих элементы различных типов данных.</xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2b9d4-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="2b9d4-113">Он добавляет элементы в конец каждой очереди и затем удаляет и отображает элементы из начала каждой очереди.</span><span class="sxs-lookup"><span data-stu-id="2b9d4-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     <span data-ttu-id="2b9d4-114">[!code-vb[VbVbalrDataTypes №&9;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b9d4-114">[!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b9d4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2b9d4-115">See Also</span></span>  
 <span data-ttu-id="2b9d4-116">[Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d4-116">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="2b9d4-117"> [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d4-117"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="2b9d4-118"> [Независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) </span><span class="sxs-lookup"><span data-stu-id="2b9d4-118"> [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) </span></span>  
<span data-ttu-id="2b9d4-119"> [Предложение Of (Visual Basic)](../../../../visual-basic/language-reference/statements/of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d4-119"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span></span>  
<span data-ttu-id="2b9d4-120"> [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d4-120"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="2b9d4-121"> [Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d4-121"> [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md) </span></span>  
<span data-ttu-id="2b9d4-122"> [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span><span class="sxs-lookup"><span data-stu-id="2b9d4-122"> [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span></span>
