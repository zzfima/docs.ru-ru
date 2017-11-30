---
title: "Недопустимый порядковый номер"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="9d64e-102">Недопустимый порядковый номер</span><span class="sxs-lookup"><span data-stu-id="9d64e-102">Ordinal is not valid</span></span>
<span data-ttu-id="9d64e-103">При вызове в библиотеке динамической компоновки (DLL) использовался использовать номер, а не имя процедуры, с помощью `#num` синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="9d64e-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="9d64e-104">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="9d64e-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="9d64e-105">Попытка преобразовать `#num` выражение в порядковый.</span><span class="sxs-lookup"><span data-stu-id="9d64e-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="9d64e-106">`#num` Указанного не соответствует ни одной функции в DLL.</span><span class="sxs-lookup"><span data-stu-id="9d64e-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="9d64e-107">Библиотека типов имеет недопустимое объявление причиной внутреннего использования недопустимого порядкового номера.</span><span class="sxs-lookup"><span data-stu-id="9d64e-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d64e-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9d64e-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="9d64e-109">Убедитесь, что выражение представляет допустимый номер или вызовите процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="9d64e-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="9d64e-110">Убедитесь, что `#num` определяет допустимую функцию в DLL.</span><span class="sxs-lookup"><span data-stu-id="9d64e-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="9d64e-111">Изолируйте вызов процедуры, вызывающей ошибку код комментарием.</span><span class="sxs-lookup"><span data-stu-id="9d64e-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="9d64e-112">Запись `Declare` инструкции для процедуры и сообщите об ошибке разработчику библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="9d64e-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d64e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9d64e-113">See Also</span></span>  
 [<span data-ttu-id="9d64e-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="9d64e-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
