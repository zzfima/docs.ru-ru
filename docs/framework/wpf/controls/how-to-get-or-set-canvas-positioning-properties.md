---
title: Практическое руководство. Получение или определение свойств размещения холста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910485"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="f1c4b-102">Практическое руководство. Получение или определение свойств размещения холста</span><span class="sxs-lookup"><span data-stu-id="f1c4b-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="f1c4b-103">В этом примере показано, как использовать методы размещения элемента <xref:System.Windows.Controls.Canvas> для размещения содержимого дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="f1c4b-104">В этом примере используется содержимое в <xref:System.Windows.Controls.ListBoxItem> для представления значений размещения и преобразования их в экземпляры <xref:System.Double>, который является обязательным аргументом для позиционирования.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="f1c4b-105">Значения преобразуются обратно в строки и отображаются в виде текста в <xref:System.Windows.Controls.TextBlock> элемента с помощью <xref:System.Windows.Controls.Canvas.GetLeft%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1c4b-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f1c4b-106">Example</span></span>  
 <span data-ttu-id="f1c4b-107">В следующем примере создается <xref:System.Windows.Controls.ListBox> элемент, который содержит одиннадцать выбираемых <xref:System.Windows.Controls.ListBoxItem> элементов.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="f1c4b-108"><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Триггеров событий `ChangeLeft` пользовательский метод, который определяет последующего блока кода.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="f1c4b-109">Каждый <xref:System.Windows.Controls.ListBoxItem> представляет <xref:System.Double> значение, которое является одним из аргументов, <xref:System.Windows.Controls.Canvas.SetLeft%2A> метод <xref:System.Windows.Controls.Canvas> принимает.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="f1c4b-110">Чтобы использовать <xref:System.Windows.Controls.ListBoxItem> для представления экземпляра <xref:System.Double>, необходимо сначала преобразовать <xref:System.Windows.Controls.ListBoxItem> для правильного типа данных.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="f1c4b-111">Когда пользователь изменяет <xref:System.Windows.Controls.ListBox> выбора, он вызывает `ChangeLeft` пользовательский метод.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="f1c4b-112">Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.LengthConverter> объект, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Double> (Обратите внимание, что это значение уже был преобразован в <xref:System.String> с помощью <xref:System.Windows.Controls.Control.ToString%2A> метод).</span><span class="sxs-lookup"><span data-stu-id="f1c4b-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="f1c4b-113">Это значение затем передается обратно в <xref:System.Windows.Controls.Canvas.SetLeft%2A> и <xref:System.Windows.Controls.Canvas.GetLeft%2A> методы <xref:System.Windows.Controls.Canvas> Чтобы изменить положение `text1` объекта.</span><span class="sxs-lookup"><span data-stu-id="f1c4b-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f1c4b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f1c4b-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="f1c4b-115">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="f1c4b-115">Panels Overview</span></span>](panels-overview.md)
