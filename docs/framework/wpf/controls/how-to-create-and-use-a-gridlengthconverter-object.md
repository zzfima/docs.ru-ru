---
title: Практическое руководство. Создание и использование объекта GridLengthConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770778"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="28d48-102">Практическое руководство. Создание и использование объекта GridLengthConverter</span><span class="sxs-lookup"><span data-stu-id="28d48-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="28d48-103">Пример</span><span class="sxs-lookup"><span data-stu-id="28d48-103">Example</span></span>  
 <span data-ttu-id="28d48-104">В следующем примере показано, как создать и использовать экземпляр <xref:System.Windows.GridLengthConverter>.</span><span class="sxs-lookup"><span data-stu-id="28d48-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="28d48-105">В примере определяется пользовательский метод с именем `changeCol`, который передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.GridLengthConverter> , преобразующий <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Windows.GridLength>.</span><span class="sxs-lookup"><span data-stu-id="28d48-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="28d48-106">Преобразованное значение затем передается обратно в качестве значения <xref:System.Windows.Controls.ColumnDefinition.Width%2A> свойство <xref:System.Windows.Controls.ColumnDefinition> элемент.</span><span class="sxs-lookup"><span data-stu-id="28d48-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="28d48-107">В примере также определяется второй пользовательский метод с именем `changeColVal`.</span><span class="sxs-lookup"><span data-stu-id="28d48-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="28d48-108">Этот пользовательский метод преобразует <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> из <xref:System.Windows.Controls.Slider> для <xref:System.String> и затем передает значение обратно <xref:System.Windows.Controls.ColumnDefinition> как <xref:System.Windows.Controls.ColumnDefinition.Width%2A> элемента.</span><span class="sxs-lookup"><span data-stu-id="28d48-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="28d48-109">Обратите внимание, что отдельный [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл определяет содержание <xref:System.Windows.Controls.ListBoxItem>.</span><span class="sxs-lookup"><span data-stu-id="28d48-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="28d48-110">См. также</span><span class="sxs-lookup"><span data-stu-id="28d48-110">See also</span></span>

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
