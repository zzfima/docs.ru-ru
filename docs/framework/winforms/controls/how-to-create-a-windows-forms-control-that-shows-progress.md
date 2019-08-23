---
title: Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms
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
ms.openlocfilehash: 84f0caace70f9877e84fdd01dc69216dc10fe485
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950578"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="8dcf3-102">Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8dcf3-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="8dcf3-103">В следующем примере кода показан пользовательский элемент управления `FlashTrackBar`, который позволяет показывать пользователю уровень или ход выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="8dcf3-104">Ход выполнения отображается с помощью градиента.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="8dcf3-105">Элемент управления `FlashTrackBar` иллюстрирует следующие концепции.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
- <span data-ttu-id="8dcf3-106">Определение пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-106">Defining custom properties.</span></span>  
  
- <span data-ttu-id="8dcf3-107">Определение пользовательских событий.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-107">Defining custom events.</span></span> <span data-ttu-id="8dcf3-108">(`FlashTrackBar` определяет событие `ValueChanged`.)</span><span class="sxs-lookup"><span data-stu-id="8dcf3-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
- <span data-ttu-id="8dcf3-109">Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> метода для предоставления логики для рисования элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
- <span data-ttu-id="8dcf3-110">Вычисление области, доступной для рисования элемента управления, с <xref:System.Windows.Forms.Control.ClientRectangle%2A> помощью его свойства.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="8dcf3-111">`FlashTrackBar` выполняет это действие в методе `OptimizedInvalidate`.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
- <span data-ttu-id="8dcf3-112">Реализация сериализации (устойчивости) для свойства при его изменении в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="8dcf3-113">`FlashTrackBar` определяет методы `ShouldSerializeStartColor` и `ShouldSerializeEndColor` для сериализации свойств `StartColor` и `EndColor`.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="8dcf3-114">В приведенной ниже таблице показаны пользовательские свойства, которые определяет `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="8dcf3-115">Свойство.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-115">Property</span></span>|<span data-ttu-id="8dcf3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8dcf3-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="8dcf3-117">Указывает, может ли пользователь изменить значение полосы прокрутки флеш-памяти, щелкнув его и перетащив.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="8dcf3-118">Определяет конечный цвет полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="8dcf3-119">Определяет степень затемнения фона относительно градиента переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="8dcf3-120">Определяет максимальное значение полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="8dcf3-121">Определяет минимальное значение полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="8dcf3-122">Определяет начальный цвет градиента.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="8dcf3-123">Указывает, следует ли отображать процент поверх градиента.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="8dcf3-124">Указывает, следует ли отображать текущее значение поверх градиента.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="8dcf3-125">Указывает, следует ли отображать на полосе прокрутки цветной градиент, отображающий текущее значение.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="8dcf3-126">Определяет текущее значение полосы ползунка.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="8dcf3-127">В следующей таблице показаны дополнительные элементы, определяемые событием изменения свойства `FlashTrackBar:` и методом, который вызывает это событие.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="8dcf3-128">Член</span><span class="sxs-lookup"><span data-stu-id="8dcf3-128">Member</span></span>|<span data-ttu-id="8dcf3-129">Описание</span><span class="sxs-lookup"><span data-stu-id="8dcf3-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="8dcf3-130">Событие, которое возникает при изменении свойства `Value` полосы ползунка.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="8dcf3-131">Метод, который вызывает событие `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="8dcf3-132">`FlashTrackBar`использует класс для данных события и <xref:System.EventHandler> для делегата события. <xref:System.EventArgs></span><span class="sxs-lookup"><span data-stu-id="8dcf3-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="8dcf3-133">Для управления соответствующими событиями `FlashTrackBar` *EventName* переопределяет следующие методы, которые он наследует от <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="8dcf3-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="8dcf3-134">Чтобы обрабатывались соответствующие события изменения свойств, `FlashTrackBar` переопределяет следующие методы, от <xref:System.Windows.Forms.Control?displayProperty=nameWithType>которых он наследует:</span><span class="sxs-lookup"><span data-stu-id="8dcf3-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="8dcf3-135">Пример</span><span class="sxs-lookup"><span data-stu-id="8dcf3-135">Example</span></span>  
 <span data-ttu-id="8dcf3-136">Элемент управления `FlashTrackBar` определяет два редактора типов пользовательского интерфейса, `FlashTrackBarValueEditor` и `FlashTrackBarDarkenByEditor`, указанные в приведенных ниже листингах кода.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="8dcf3-137">Класс `HostApp` использует элемент управления `FlashTrackBar` в форме Windows.</span><span class="sxs-lookup"><span data-stu-id="8dcf3-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="8dcf3-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8dcf3-138">See also</span></span>

- <span data-ttu-id="8dcf3-139">[Расширения поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="8dcf3-139">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="8dcf3-140">Основы разработки элементов управления форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8dcf3-140">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)
