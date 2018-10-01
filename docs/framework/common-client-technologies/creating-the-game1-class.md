---
title: Создание класса Game1
ms.date: 03/30/2017
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
ms.openlocfilehash: 368da9df4dffc7017abb02888bc2eb2641f04b8b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47201027"
---
# <a name="creating-the-game1-class"></a>Создание класса Game1
Как во всех проектах Microsof XNA, класс Game1 является производным от класса [Microsoft.Xna.Framework.Game](https://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx), который предоставляет инициализацию основного графического устройства, логику игры и код отрисовки для игр XNA. Класс Game1 довольно простой, поскольку большая часть работы выполняется в классах GamePiece и GamePieceCollection.  
  
## <a name="creating-the-code"></a>Создание кода  
 Закрытые члены класса состоят из объекта **GamePieceCollection** для хранения элементов игры, объекта [GraphicsDeviceManager](https://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) и объекта [SpriteBatch](https://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx), используемого для отрисовки элементов игры.  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 Экземпляры этих объектов создаются во время инициализации игры.  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 При вызове метода [LoadContent](https://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) создаются элементы игры и назначаются объекту **GamePieceCollection**. Существует два типа элементов игры. Коэффициент масштабирования для элементов слегка отличается, поэтому одни элементы могут стать меньше, а другие больше.  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 Метод [Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) несколько раз вызывается XNA Framework во время выполнения игры. Метод [Update](https://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) вызывает методы **ProcessInertia** и **UpdateFromMouse** в коллекции элементов игры. Эти методы описаны в разделе [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 Метод [Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) также вызывается XNA Framework несколько раз во время выполнения игры. Метод [Draw](https://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) выполняет отрисовку элементов игры путем вызова метода **Draw** объекта **GamePieceCollection**. Этот метод описывается в разделе [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a>См. также  
 [Манипуляции и инерция](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Использование манипуляций и инерции в приложении XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Создание класса GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [Полные листинги кода](../../../docs/framework/common-client-technologies/full-code-listings.md)
