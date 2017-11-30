---
title: "Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d19ac8b03b992eb9b09b5cb45fdcceadad3a822a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="c9ef0-102">Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9ef0-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="c9ef0-103">При использовании инициализатора коллекции для создания коллекции, компилятор Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метод соответствуют типам значений в инициализаторе коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9ef0-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="c9ef0-104">Это `Add` метод используется для заполнения коллекции со значениями из инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9ef0-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="c9ef0-105">Если совпадений `Add` метод существует и не может изменить код для коллекции, можно добавить метод расширения вызывается `Add` с параметрами, которые требуются в инициализаторе коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9ef0-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="c9ef0-106">Обычно это необходимо делать, если использовать инициализаторы коллекции для универсальных коллекций.</span><span class="sxs-lookup"><span data-stu-id="c9ef0-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9ef0-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c9ef0-107">Example</span></span>  
 <span data-ttu-id="c9ef0-108">Следующий пример демонстрирует добавление метода расширения к универсальному <xref:System.Collections.Generic.List%601> тип, так что можно использовать инициализатор коллекции для добавления объектов определенного типа `Employee`.</span><span class="sxs-lookup"><span data-stu-id="c9ef0-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="c9ef0-109">Метод расширения позволяет использовать сокращенный синтаксис инициализатора набора.</span><span class="sxs-lookup"><span data-stu-id="c9ef0-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c9ef0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c9ef0-110">See Also</span></span>  
 [<span data-ttu-id="c9ef0-111">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="c9ef0-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="c9ef0-112">Практическое руководство. Создание коллекции, используемой инициализатором набора</span><span class="sxs-lookup"><span data-stu-id="c9ef0-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
