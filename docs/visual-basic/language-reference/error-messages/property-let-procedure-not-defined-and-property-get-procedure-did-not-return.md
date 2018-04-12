---
title: Процедура свойства let не определена, а процедура свойства get не вернула объект
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b043ca698a9c90afd41de90c7dbc5879ae7de623
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a><span data-ttu-id="2af1b-102">Процедура свойства let не определена, а процедура свойства get не вернула объект</span><span class="sxs-lookup"><span data-stu-id="2af1b-102">Property let procedure not defined and property get procedure did not return an object</span></span>
<span data-ttu-id="2af1b-103">Некоторые свойства, методы и операции применимы только к `Collection` объектов.</span><span class="sxs-lookup"><span data-stu-id="2af1b-103">Certain properties, methods, and operations can only apply to `Collection` objects.</span></span> <span data-ttu-id="2af1b-104">Указанные операция или свойство применимы только к коллекциям, но объект не является коллекцией.</span><span class="sxs-lookup"><span data-stu-id="2af1b-104">You specified an operation or property that is exclusive to collections, but the object is not a collection.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2af1b-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2af1b-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="2af1b-106">Проверьте правильность написания имени объекта или свойства или убедитесь, что объект является `Collection` объекта.</span><span class="sxs-lookup"><span data-stu-id="2af1b-106">Check the spelling of the object or property name, or verify that the object is a `Collection` object.</span></span>  
  
2.  <span data-ttu-id="2af1b-107">Посмотрите на `Add` метод, используемый для добавления в коллекцию, чтобы убедитесь, что синтаксис правильный, и все идентификаторы, правильность написания.</span><span class="sxs-lookup"><span data-stu-id="2af1b-107">Look at the `Add` method used to add the object to the collection to be sure the syntax is correct and that any identifiers were spelled correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af1b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2af1b-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Collection>
