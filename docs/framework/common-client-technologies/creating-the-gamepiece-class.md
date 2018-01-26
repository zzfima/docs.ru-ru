---
title: "Создание класса GamePiece"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a27a86-ac1c-47be-b477-cb4b819459d3
caps.latest.revision: "9"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51494801773ac8724c2ca5392df8cb013e989466
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-gamepiece-class"></a>Создание класса GamePiece
Класс **GamePiece** инкапсулирует все функциональные возможности, необходимые для загрузки изображения элемента игры Microsoft XNA, отслеживания состояния мыши относительно элемента игры, захвата мыши, обеспечения обработки манипуляции и инерции, а также обеспечения возможности возвращения, когда элемент игры достигнет ограничений порта просмотра.  
  
## <a name="private-members"></a>Закрытые члены  
 В верхней части класса **GamePiece** объявляется несколько закрытых членов.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privatemembers)]  
  
## <a name="public-properties"></a>Открытые свойства  
 Три из этих закрытых членов предоставляются через открытые свойства. Свойства **Scale** и **PieceColor** позволяют приложению задавать соответственно масштаб и цвет элемента. Свойство **Bounds** предоставляется, чтобы разрешить одному элементу использовать границы другого элемента для своей отрисовки, например когда один элемент должен накладываться на другой. В следующем коде показано объявление открытых свойств.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PublicProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_publicproperties)]  
  
## <a name="class-constructor"></a>Конструктор класса  
 Конструктор класса **GamePiece** принимает следующие параметры.  
  
-   Тип [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx). Ссылка, передаваемая здесь, назначается закрытому члену `spriteBatch` и используется для доступа к методу [SpriteBatch.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.draw.aspx), когда элемент игры отрисовывается сам. Кроме того, свойство [GraphicsDevice](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.graphicsdevice.aspx) используется для создания объекта [Texture](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.texture.aspx), связанного с элементом игры, а также для получения размера порта просмотра для обнаружения, когда элемент игры встретит границу окна, чтобы этот элемент мог вернуться.  
  
-   Строка, указывающая имя файла изображения, используемого для элемента игры.  
  
 Этот конструктор также создает объект <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D> и объект <xref:System.Windows.Input.Manipulations.InertiaProcessor2D>, а также устанавливает обработчики событий для их событий.  
  
 В следующем коде показан конструктор класса **GamePiece**.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Constructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_constructor)]  
  
## <a name="capturing-mouse-input"></a>Захват ввода мыши  
 Метод **UpdateFromMouse** отвечает за обнаружение нажатия кнопки мыши, когда указатель мыши находится в пределах границ элемента игры, и обнаружение освобождения кнопки мыши.  
  
 При нажатии левой кнопки мыши (когда указатель мыши находится в пределах границ элемента) этот метод устанавливает флаг, указывающий, что этот элемент игры захватил мышь, и начинает обработку манипуляции.  
  
 Обработка манипуляции начинается с создания массива объектов <xref:System.Windows.Input.Manipulations.Manipulator2D> и передачи их в объект <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D>. Это заставляет обработчик манипуляции оценить манипуляторы (в данном случае один манипулятор) и инициировать события манипуляции.  
  
 Кроме того, точка, в которой возникает перетаскивание, сохраняется. Она используется позднее, во время события <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta>, для настройки разностных значений транзакций, чтобы элемент игры поворачивался в строку за точкой перетаскивания.  
  
 Наконец, этот метод возвращает состояние захвата мыши. Это позволяет объекту [GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md) управлять захватом при наличии нескольких элементов игры.  
  
 В следующем примере кода показан метод **UpdateFromMouse**.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_updatefrommouse)]  
  
## <a name="processing-manipulations"></a>Обработка манипуляций  
 В начале манипуляции возникает событие <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Started>. Обработчик этого события останавливает обработку инерции, если она выполняется, и устанавливает для флага *processInertia* значение `false`.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationStarted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationstarted)]  
  
 При изменении значений, связанных с этой манипуляцией, возникает событие <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Delta>. Обработчик этого события использует разностные значения, переданные в аргументы событий, для изменения значений положения и поворота элемента игры.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationdelta)]  
  
 При удалении всех манипуляторов (в данном случае одного манипулятора), связанных с манипуляцией, обработчик манипуляции инициирует событие <xref:System.Windows.Input.Manipulations.ManipulationProcessor2D.Completed>. Обработчик этого события запускает обработку инерции, устанавливая для начальных скоростей обработчика инерции значения, сообщенные в аргументах события, и устанавливает для флага *processInertia* значение `true`.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnManipulationCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_onmanipulationcompleted)]  
  
## <a name="processing-inertia"></a>Обработка инерции  
 Когда обработка инерции экстраполирует новые значения для угловой и линейной скоростей, координат положения (перевода) и поворота, вызывается событие <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>. Обработчик этого события использует разностные значения, переданные в аргументы событий, для изменения положения и поворота элемента игры.  
  
 Если новые координаты приводят к перемещению элемента игры за границы порта просмотра, скорость обработки инерции поворачивается в обратном направлении. Это приводит к повороту элемента игры от встреченной границы порта просмотра.  
  
 Вы не можете изменять свойства объекта <xref:System.Windows.Input.Manipulations.InertiaProcessor2D> во время выполнения экстраполяции. Таким образом, при обращении скорости X или Y обработчик события сначала останавливает инерцию путем вызова метода <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Complete%2A>. Затем он назначает новые начальные значения скорости текущими значениями (с учетом неупругого поведения) и устанавливает для флага *processInertia* значение `true`.  
  
 В следующем примере кода показан обработчик событий для события <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaDelta](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiadelta)]  
  
 После завершения обработки инерции обработчик инерции вызывает событие <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Completed>. Обработчик для этого события устанавливает флаг *processInertia* в значение `false`.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_OnInertiaCompleted](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_oninertiacompleted)]  
  
 Ни одна из логик, представленных выше, в действительности не вызывает выполнение экстраполяции инерции. Это выполняется в методе **ProcessInertia**. Этот метод, который повторно вызывается из цикла обновления игры (метод [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx)), проверяет, имеет ли флаг *processInertia* значение `true`, и если да, вызывает метод <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Process%2A>. Вызов этого метода приводит к выполнению экстраполяции и вызывает событие <xref:System.Windows.Input.Manipulations.InertiaProcessor2D.Delta>.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_ProcessInertia](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_processinertia)]  
  
 Элемент игры фактически не отображается до тех пор, пока не будет вызвана одна из перегрузок метода Draw. Первая перегрузка этого метода вызывается повторно из цикла рисования игры (метод [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx)). Это отрисовывает элемент игры с текущим положением, поворотом и масштабом.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_Draw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_draw)]  
  
## <a name="additional-properties"></a>Дополнительные свойства  
 Класс **GamePiece** использует три закрытых свойства.  
  
1.  **Timestamp** — получает значение метки времени, которая будет использоваться обработчиками манипуляции и инерции.  
  
2.  **X** — возвращает или задает координату X элемента игры. Если это свойство установлено, то настраивает границы, используемые для проверки попадания и места поворота обработчика манипуляции.  
  
3.  **Y** — возвращает или задает координату Y элемента игры. Если это свойство установлено, то настраивает границы, используемые для проверки попадания и места поворота обработчика манипуляции.  
  
 [!code-csharp[ManipulationXNA#_GamePiece_PrivateProperties](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiece.cs#_gamepiece_privateproperties)]  
  
## <a name="see-also"></a>См. также  
 [Манипуляции и инерция](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [Использование манипуляций и инерции в приложении XNA](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [Создание класса GamePieceCollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [Создание класса Game1](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)
