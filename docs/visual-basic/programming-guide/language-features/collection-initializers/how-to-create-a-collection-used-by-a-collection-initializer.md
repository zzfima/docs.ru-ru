---
title: Как выполнить Создание коллекции, используемой инициализатором набора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: aaa367e5a1739f26e9b0458d8f2fc44462b73b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631728"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="7064c-102">Как выполнить Создание коллекции, используемой инициализатором набора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7064c-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="7064c-103">При использовании инициализатора коллекции для создания коллекции, используемые компилятором Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе набора.</span><span class="sxs-lookup"><span data-stu-id="7064c-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="7064c-104">Это `Add` метод используется для заполнения коллекции значениями из инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="7064c-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7064c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="7064c-105">Example</span></span>  
 <span data-ttu-id="7064c-106">В следующем примере показан `OrderCollection` коллекцию, содержащую общедоступный `Add` метод, который можно использовать инициализатор коллекции для добавления объектов определенного типа `Order`.</span><span class="sxs-lookup"><span data-stu-id="7064c-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="7064c-107">`Add` Метода позволяет использовать сокращенный синтаксис инициализатора набора.</span><span class="sxs-lookup"><span data-stu-id="7064c-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7064c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="7064c-108">See also</span></span>
- [<span data-ttu-id="7064c-109">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="7064c-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="7064c-110">Практическое руководство. Создание метода Add, расширение используемого инициализатором набора</span><span class="sxs-lookup"><span data-stu-id="7064c-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
