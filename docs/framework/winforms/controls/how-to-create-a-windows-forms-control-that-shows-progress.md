---
title: Как выполнить Создание элемента управления Windows Forms, показывающего прогресс
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: c474419d1b60d8dbc937e77251b877efca2709b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594724"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="1a0dc-102">Как выполнить Создание элемента управления Windows Forms, показывающего прогресс</span><span class="sxs-lookup"><span data-stu-id="1a0dc-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="1a0dc-103">В следующем примере кода показан пользовательский элемент управления `FlashTrackBar`, который позволяет показывать пользователю уровень или ход выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="1a0dc-104">Ход выполнения отображается с помощью градиента.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="1a0dc-105">Элемент управления `FlashTrackBar` иллюстрирует следующие концепции.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
-   <span data-ttu-id="1a0dc-106">Определение пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-106">Defining custom properties.</span></span>  
  
-   <span data-ttu-id="1a0dc-107">Определение пользовательских событий.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-107">Defining custom events.</span></span> <span data-ttu-id="1a0dc-108">(`FlashTrackBar` определяет событие `ValueChanged`.)</span><span class="sxs-lookup"><span data-stu-id="1a0dc-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
-   <span data-ttu-id="1a0dc-109">Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> метод для предоставления логики для отрисовки элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
-   <span data-ttu-id="1a0dc-110">Расчет области, доступной для рисования элемента управления с помощью его <xref:System.Windows.Forms.Control.ClientRectangle%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="1a0dc-111">`FlashTrackBar` выполняет это действие в методе `OptimizedInvalidate`.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
-   <span data-ttu-id="1a0dc-112">Реализация сериализации (устойчивости) для свойства при его изменении в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="1a0dc-113">`FlashTrackBar` определяет методы `ShouldSerializeStartColor` и `ShouldSerializeEndColor` для сериализации свойств `StartColor` и `EndColor`.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="1a0dc-114">В приведенной ниже таблице показаны пользовательские свойства, которые определяет `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="1a0dc-115">Свойство.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-115">Property</span></span>|<span data-ttu-id="1a0dc-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="1a0dc-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="1a0dc-117">Указывает, может ли пользователь изменить значение полосы прокрутки флеш-памяти, щелкнув его и перетащив.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="1a0dc-118">Определяет конечный цвет полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="1a0dc-119">Определяет степень затемнения фона относительно градиента переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="1a0dc-120">Определяет максимальное значение полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="1a0dc-121">Определяет минимальное значение полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="1a0dc-122">Определяет начальный цвет градиента.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="1a0dc-123">Указывает, следует ли отображать процент поверх градиента.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="1a0dc-124">Указывает, следует ли отображать текущее значение поверх градиента.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="1a0dc-125">Указывает, следует ли отображать на полосе прокрутки цветной градиент, отображающий текущее значение.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="1a0dc-126">Определяет текущее значение полосы ползунка.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="1a0dc-127">В следующей таблице показаны дополнительные элементы, определяемые событием изменения свойства `FlashTrackBar:` и методом, который вызывает это событие.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="1a0dc-128">Член</span><span class="sxs-lookup"><span data-stu-id="1a0dc-128">Member</span></span>|<span data-ttu-id="1a0dc-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="1a0dc-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="1a0dc-130">Событие, которое возникает при изменении свойства `Value` полосы ползунка.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="1a0dc-131">Метод, который вызывает событие `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="1a0dc-132">`FlashTrackBar` использует <xref:System.EventArgs> класс данных события и <xref:System.EventHandler> для делегата события.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="1a0dc-133">Для обработки соответствующих *EventName* события, `FlashTrackBar` переопределяет следующие методы, которые он наследует от <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1a0dc-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="1a0dc-134">Для обработки соответствующих событий изменения свойств `FlashTrackBar` переопределяет следующие методы, которые он наследует от <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1a0dc-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="1a0dc-135">Пример</span><span class="sxs-lookup"><span data-stu-id="1a0dc-135">Example</span></span>  
 <span data-ttu-id="1a0dc-136">Элемент управления `FlashTrackBar` определяет два редактора типов пользовательского интерфейса, `FlashTrackBarValueEditor` и `FlashTrackBarDarkenByEditor`, указанные в приведенных ниже листингах кода.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="1a0dc-137">Класс `HostApp` использует элемент управления `FlashTrackBar` в форме Windows.</span><span class="sxs-lookup"><span data-stu-id="1a0dc-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="1a0dc-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1a0dc-138">See also</span></span>
- [<span data-ttu-id="1a0dc-139">Расширения поддержки времени разработки</span><span class="sxs-lookup"><span data-stu-id="1a0dc-139">Extending Design-Time Support</span></span>](https://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)
- [<span data-ttu-id="1a0dc-140">Основы разработки элементов управления форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a0dc-140">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)
