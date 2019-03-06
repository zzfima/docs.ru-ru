---
title: Практическое руководство. Задание стиля строки в ListView, который реализует GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 0c8806c399959fdc1466e0839ba469881718092b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361633"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="21dfd-102">Практическое руководство. Задание стиля строки в ListView, который реализует GridView</span><span class="sxs-lookup"><span data-stu-id="21dfd-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="21dfd-103">В этом примере показано, как изменить стиль строки в <xref:System.Windows.Controls.ListView> управления, который реализует <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> режим.</span><span class="sxs-lookup"><span data-stu-id="21dfd-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21dfd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="21dfd-104">Example</span></span>  
 <span data-ttu-id="21dfd-105">Задать стиль строки в <xref:System.Windows.Controls.ListView> управления <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> на <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="21dfd-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="21dfd-106">Задать стиль для своих элементов, которые отображаются в виде <xref:System.Windows.Controls.ListViewItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="21dfd-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="21dfd-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Ссылки <xref:System.Windows.Controls.ControlTemplate> объекты, которые используются для отображения содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="21dfd-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="21dfd-108">Полный пример, из которого взяты следующие примеры, отображает коллекцию сведений о композициях, хранящихся в базе данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21dfd-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="21dfd-109">Каждая композиция в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки со сведениями о композиции.</span><span class="sxs-lookup"><span data-stu-id="21dfd-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="21dfd-110">В следующем примере показано определение <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих композиции в коллекции композиций.</span><span class="sxs-lookup"><span data-stu-id="21dfd-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="21dfd-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Ссылки <xref:System.Windows.Controls.ControlTemplate> объекты, определяющие способ отображения строки со сведениями о композиции.</span><span class="sxs-lookup"><span data-stu-id="21dfd-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="21dfd-112">В следующем примере показан <xref:System.Windows.Controls.ControlTemplate> , добавляет текстовую строку `"Strongly Recommended"` в строку.</span><span class="sxs-lookup"><span data-stu-id="21dfd-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="21dfd-113">Этот шаблон ссылается на <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображает, если оценка песни имеет значение 5 (пять).</span><span class="sxs-lookup"><span data-stu-id="21dfd-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="21dfd-114"><xref:System.Windows.Controls.ControlTemplate> Включает в себя <xref:System.Windows.Controls.GridViewRowPresenter> объект, который размещает содержимое строки в столбцах в соответствии с определением <xref:System.Windows.Controls.GridView> режим просмотра.</span><span class="sxs-lookup"><span data-stu-id="21dfd-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="21dfd-115">В следующем примере определяется <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="21dfd-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="21dfd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="21dfd-116">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="21dfd-117">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="21dfd-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="21dfd-118">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="21dfd-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="21dfd-119">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="21dfd-119">Styling and Templating</span></span>](styling-and-templating.md)
