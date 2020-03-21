---
title: Практическое руководство. Вывод текста по контуру
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186857"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="a479c-102">Практическое руководство. Вывод текста по контуру</span><span class="sxs-lookup"><span data-stu-id="a479c-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="a479c-103">В большинстве случаев, когда вы добавляете [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] орнамент в текстовые строки в приложении, вы используете текст с точки зрения коллекции дискретных символов, или глифов.</span><span class="sxs-lookup"><span data-stu-id="a479c-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="a479c-104">Например, можно создать линейную градиентную <xref:System.Windows.Controls.Control.Foreground%2A> кисть <xref:System.Windows.Controls.TextBox> и применить ее к свойству объекта.</span><span class="sxs-lookup"><span data-stu-id="a479c-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="a479c-105">При отображении или редактировании текстового окна линейная кисти градиента автоматически наносится на текущий набор символов в текстовой строке.</span><span class="sxs-lookup"><span data-stu-id="a479c-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Текст, отображенный при помощи кисти линейного градиента](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="a479c-107">Тем не менее, вы <xref:System.Windows.Media.Geometry> также можете преобразовать текст в объекты, что позволяет создавать другие типы визуально богатого текста.</span><span class="sxs-lookup"><span data-stu-id="a479c-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="a479c-108">Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура строки текста.</span><span class="sxs-lookup"><span data-stu-id="a479c-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="a479c-110">Когда текст преобразуется <xref:System.Windows.Media.Geometry> в объект, он больше не представляет собой набор символов, вы не можете изменить символы в строке текста.</span><span class="sxs-lookup"><span data-stu-id="a479c-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="a479c-111">Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки.</span><span class="sxs-lookup"><span data-stu-id="a479c-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="a479c-112">Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста.</span><span class="sxs-lookup"><span data-stu-id="a479c-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="a479c-113">Следующие примеры иллюстрируют несколько способов создания визуальных эффектов путем изменения штриха и заполнения преобразованного текста.</span><span class="sxs-lookup"><span data-stu-id="a479c-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Текст с различными цветами для заполнения штриха](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="a479c-116">Также можно изменить прямоугольник ящика или выделить преобразованный текст.</span><span class="sxs-lookup"><span data-stu-id="a479c-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="a479c-117">Следующий пример иллюстрирует способ создания визуальных эффектов путем изменения штриха и выделения преобразованного текста.</span><span class="sxs-lookup"><span data-stu-id="a479c-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Текст с изображением кисти, нанесенной на штрих и выделение](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="a479c-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a479c-119">Example</span></span>  
 <span data-ttu-id="a479c-120">Ключом к преобразованию <xref:System.Windows.Media.Geometry> текста в <xref:System.Windows.Media.FormattedText> объект является использование объекта.</span><span class="sxs-lookup"><span data-stu-id="a479c-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="a479c-121">После создания этого объекта можно использовать <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> методы для преобразования <xref:System.Windows.Media.Geometry> текста в объекты.</span><span class="sxs-lookup"><span data-stu-id="a479c-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="a479c-122">Первый метод возвращает геометрию отформатированный текст; второй метод возвращает геометрию ограниченного окна отформатированный текст.</span><span class="sxs-lookup"><span data-stu-id="a479c-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="a479c-123">Следующий пример кода показывает, <xref:System.Windows.Media.FormattedText> как создать объект и получить геометрию отформатированного текста и его ограничивающего окна.</span><span class="sxs-lookup"><span data-stu-id="a479c-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="a479c-124">Для отображения <xref:System.Windows.Media.Geometry> извлеченных объектов необходимо <xref:System.Windows.Media.DrawingContext> получить доступ к объекту, отображаемому преобразованный текст.</span><span class="sxs-lookup"><span data-stu-id="a479c-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="a479c-125">В этих примерах кода это делается путем создания пользовательского объекта управления, который происходит от класса, который поддерживает пользовательский рендеринг.</span><span class="sxs-lookup"><span data-stu-id="a479c-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="a479c-126">Для <xref:System.Windows.Media.Geometry> отображения объектов в пользовательском элементе управления предоставьте переопределение для метода. <xref:System.Windows.UIElement.OnRender%2A></span><span class="sxs-lookup"><span data-stu-id="a479c-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="a479c-127">Ваш перекрывшийся <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> метод должен <xref:System.Windows.Media.Geometry> использовать метод для рисования объектов.</span><span class="sxs-lookup"><span data-stu-id="a479c-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="a479c-128">Для источника пользовательского объекта пользовательского управления можно найти [OutlineTextControl.cs для C-и](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) [OutlineTextControl.vb для Visual Basic.](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)</span><span class="sxs-lookup"><span data-stu-id="a479c-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a479c-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a479c-129">See also</span></span>

- [<span data-ttu-id="a479c-130">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="a479c-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
