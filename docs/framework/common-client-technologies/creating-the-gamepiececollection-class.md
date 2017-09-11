---
title: "Создание класса GamePieceCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: 8
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b74702d71113c3a9dac654971e7d02f97016218b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="91b53-102">Создание класса GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="91b53-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="91b53-103">Класс **GamePieceCollection** является производным от универсального класса List и предоставляет методы для упрощения управления несколькими объектами **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="91b53-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="91b53-104">Создание кода</span><span class="sxs-lookup"><span data-stu-id="91b53-104">Creating the Code</span></span>  
 <span data-ttu-id="91b53-105">Конструктор класса **GamePieceCollection** инициализирует закрытый член *capturedIndex*.</span><span class="sxs-lookup"><span data-stu-id="91b53-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="91b53-106">Это поле используется для отслеживания, какой элемент игры в настоящее время захвачен мышью.</span><span class="sxs-lookup"><span data-stu-id="91b53-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 <span data-ttu-id="91b53-107">[!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]</span><span class="sxs-lookup"><span data-stu-id="91b53-107">[!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]</span></span>  
  
 <span data-ttu-id="91b53-108">Методы **ProcessInertia** и **Draw** упрощают код, необходимый в методах [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) и [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) игры, перечисляя все элементы игры в коллекции и вызывая соответствующий метод в каждом объекте **GamePiece**.</span><span class="sxs-lookup"><span data-stu-id="91b53-108">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 <span data-ttu-id="91b53-109">[!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]</span><span class="sxs-lookup"><span data-stu-id="91b53-109">[!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]</span></span>  
  
 <span data-ttu-id="91b53-110">Метод **UpdateFromMouse** также вызывается во время обновления игры.</span><span class="sxs-lookup"><span data-stu-id="91b53-110">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="91b53-111">Он разрешает только одному элементу игры быть захваченным мышью, сначала выполняя проверку, не действует ли еще текущий захват (если он имеется).</span><span class="sxs-lookup"><span data-stu-id="91b53-111">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="91b53-112">Если захват еще действует, никаким другим элементам игры не разрешается проверять наличие захвата.</span><span class="sxs-lookup"><span data-stu-id="91b53-112">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="91b53-113">Если в текущий момент никакой элемент не захвачен, метод **UpdateFromMouse** перечисляет все элементы игры с последнего до первого и проверяет, сообщает ли этот элемент о захвате мышью.</span><span class="sxs-lookup"><span data-stu-id="91b53-113">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="91b53-114">Если сообщает, то этот элемент становится текущим захваченным элементом, и дальнейшая обработка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="91b53-114">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="91b53-115">Метод **UpdateFromMouse** сначала проверяет последний элемент в коллекции, чтобы в случае перекрытия двух элементов захват получил элемент с более высоким Z-порядком.</span><span class="sxs-lookup"><span data-stu-id="91b53-115">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="91b53-116">Z-порядок не является ни явным, ни изменяемым; он просто зависит от порядка добавления элементов игры в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="91b53-116">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 <span data-ttu-id="91b53-117">[!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]</span><span class="sxs-lookup"><span data-stu-id="91b53-117">[!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b53-118">См. также</span><span class="sxs-lookup"><span data-stu-id="91b53-118">See Also</span></span>  
 <span data-ttu-id="91b53-119">[Манипуляции и инерция](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md) </span><span class="sxs-lookup"><span data-stu-id="91b53-119">[Manipulations and Inertia](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md) </span></span>  
 <span data-ttu-id="91b53-120">[Использование манипуляций и инерции в приложении XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md) </span><span class="sxs-lookup"><span data-stu-id="91b53-120">[Using Manipulations and Inertia in an XNA Application](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md) </span></span>  
 <span data-ttu-id="91b53-121">[Создание класса GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md) </span><span class="sxs-lookup"><span data-stu-id="91b53-121">[Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md) </span></span>  
 <span data-ttu-id="91b53-122">[Создание класса Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md) </span><span class="sxs-lookup"><span data-stu-id="91b53-122">[Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md) </span></span>  
 [<span data-ttu-id="91b53-123">Полные листинги кода</span><span class="sxs-lookup"><span data-stu-id="91b53-123">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)

