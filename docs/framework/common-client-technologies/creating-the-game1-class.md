---
title: Создание класса Game1
ms.date: 03/30/2017
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
ms.openlocfilehash: c96fa846d11947af03faec26dd6de99e0aeec052
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452801"
---
# <a name="creating-the-game1-class"></a>Создание класса Game1
Как во всех проектах Microsof XNA, класс Game1 является производным от класса [Microsoft.Xna.Framework.Game](https://docs.microsoft.com/previous-versions/windows/xna/bb197040%28v%3dxnagamestudio.41%29), который предоставляет инициализацию основного графического устройства, логику игры и код отрисовки для игр XNA. Класс Game1 довольно простой, поскольку большая часть работы выполняется в классах GamePiece и GamePieceCollection.  
  
## <a name="creating-the-code"></a>Создание кода  
 Закрытые члены класса состоят из объекта **GamePieceCollection** для хранения элементов игры, объекта [GraphicsDeviceManager](https://docs.microsoft.com/previous-versions/windows/xna/bb197317%28v%3dxnagamestudio.41%29) и объекта [SpriteBatch](https://docs.microsoft.com/previous-versions/windows/xna/bb199034%28v%3dxnagamestudio.41%29), используемого для отрисовки элементов игры.  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 Экземпляры этих объектов создаются во время инициализации игры.  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 При вызове метода [LoadContent](https://docs.microsoft.com/previous-versions/windows/xna/bb975766%28v%3dxnagamestudio.41%29) создаются элементы игры и назначаются объекту **GamePieceCollection**. Существует два типа элементов игры. Коэффициент масштабирования для элементов слегка отличается, поэтому одни элементы могут стать меньше, а другие больше.  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 Метод [Update](https://docs.microsoft.com/previous-versions/windows/xna/bb199616%28v%3dxnagamestudio.41%29) несколько раз вызывается XNA Framework во время выполнения игры. Метод [Update](https://docs.microsoft.com/previous-versions/windows/xna/bb199616%28v%3dxnagamestudio.41%29) вызывает методы **ProcessInertia** и **UpdateFromMouse** в коллекции элементов игры. Эти методы описаны в разделе [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 Метод [Draw](https://docs.microsoft.com/previous-versions/windows/xna/bb196422%28v%3dxnagamestudio.41%29) также вызывается XNA Framework несколько раз во время выполнения игры. Метод [Draw](https://docs.microsoft.com/previous-versions/windows/xna/bb196422%28v%3dxnagamestudio.41%29) выполняет отрисовку элементов игры путем вызова метода **Draw** объекта **GamePieceCollection**. Этот метод описывается в разделе [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a>См. также  
 [Манипуляции и инерция](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Использование манипуляций и инерции в приложении XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Создание класса GamePiece](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [Полные листинги кода](../../../docs/framework/common-client-technologies/full-code-listings.md)
