---
title: "Создание класса GamePieceCollection | Документы Майкрософт"
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 672d2717905195084c381ea692aa426b5e3ca09c
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---
# <a name="creating-the-gamepiececollection-class"></a>Создание класса GamePieceCollection
Класс **GamePieceCollection** является производным от универсального класса List и предоставляет методы для упрощения управления несколькими объектами **GamePiece**.  
  
## <a name="creating-the-code"></a>Создание кода  
 Конструктор класса **GamePieceCollection** инициализирует закрытый член *capturedIndex*. Это поле используется для отслеживания, какой элемент игры в настоящее время захвачен мышью.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 Методы **ProcessInertia** и **Draw** упрощают код, необходимый в методах [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) и [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) игры, перечисляя все элементы игры в коллекции и вызывая соответствующий метод в каждом объекте **GamePiece**.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 Метод **UpdateFromMouse** также вызывается во время обновления игры. Он разрешает только одному элементу игры быть захваченным мышью, сначала выполняя проверку, не действует ли еще текущий захват (если он имеется). Если захват еще действует, никаким другим элементам игры не разрешается проверять наличие захвата.  
  
 Если в текущий момент никакой элемент не захвачен, метод **UpdateFromMouse** перечисляет все элементы игры с последнего до первого и проверяет, сообщает ли этот элемент о захвате мышью. Если сообщает, то этот элемент становится текущим захваченным элементом, и дальнейшая обработка не выполняется. Метод **UpdateFromMouse** сначала проверяет последний элемент в коллекции, чтобы в случае перекрытия двух элементов захват получил элемент с более высоким Z-порядком. Z-порядок не является ни явным, ни изменяемым; он просто зависит от порядка добавления элементов игры в коллекцию.  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a>См. также  
 [Манипуляции и инерция](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)   
 [Использование манипуляций и инерции в приложении XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)   
 [Создание класса GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)   
 [Создание класса Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)   
 [Полные листинги кода](../../../docs/framework/common-client-technologies/full-code-listings.md)
