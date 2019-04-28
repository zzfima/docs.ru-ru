---
title: Практическое руководство. Создание метода Add, расширение используемого инициализатором набора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907079"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="bb95e-102">Практическое руководство. Создание метода Add, расширение используемого инициализатором набора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb95e-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="bb95e-103">При использовании инициализатора коллекции для создания коллекции, используемые компилятором Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе набора.</span><span class="sxs-lookup"><span data-stu-id="bb95e-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="bb95e-104">Это `Add` метод используется для заполнения коллекции значениями из инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="bb95e-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="bb95e-105">Если совпадающих `Add` метод существует и не может изменить код для коллекции, можно добавить метод расширения `Add` с параметрами, которые требуются для инициализатора набора.</span><span class="sxs-lookup"><span data-stu-id="bb95e-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="bb95e-106">Обычно это необходимо выполнить с помощью инициализаторов коллекций для универсальных коллекций.</span><span class="sxs-lookup"><span data-stu-id="bb95e-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb95e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="bb95e-107">Example</span></span>  
 <span data-ttu-id="bb95e-108">В следующем примере показано, как добавить метод расширения к общим <xref:System.Collections.Generic.List%601> так, чтобы инициализатора коллекции можно использовать для добавления объектов определенного типа `Employee`.</span><span class="sxs-lookup"><span data-stu-id="bb95e-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="bb95e-109">Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.</span><span class="sxs-lookup"><span data-stu-id="bb95e-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="bb95e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bb95e-110">See also</span></span>

- [<span data-ttu-id="bb95e-111">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="bb95e-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="bb95e-112">Практическое руководство. Создание коллекции, используемой инициализатором набора</span><span class="sxs-lookup"><span data-stu-id="bb95e-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
