---
title: Инструкция по Изменению стиля строки в ListView, который реализует GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733542"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="005be-102">Инструкция по Изменению стиля строки в ListView, который реализует GridView</span><span class="sxs-lookup"><span data-stu-id="005be-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="005be-103">В этом примере показано, как реализовать стиль строки в элементе управления <xref:System.Windows.Controls.ListView>, который реализует режим <xref:System.Windows.Controls.ListView.View%2A> <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="005be-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="005be-104">Пример</span><span class="sxs-lookup"><span data-stu-id="005be-104">Example</span></span>  
 <span data-ttu-id="005be-105">Можно задать стиль строки в элементе управления <xref:System.Windows.Controls.ListView>, установив <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> в элементе управления <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="005be-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="005be-106">Задайте стиль для элементов, которые представлены как <xref:System.Windows.Controls.ListViewItem> объекты.</span><span class="sxs-lookup"><span data-stu-id="005be-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="005be-107"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> ссылается на <xref:System.Windows.Controls.ControlTemplate> объекты, используемые для вывода содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="005be-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="005be-108">Полный пример, из которого извлекаются следующие примеры, отображает коллекцию сведений о песне, которые хранятся в базе данных XML.</span><span class="sxs-lookup"><span data-stu-id="005be-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="005be-109">Каждая композиция в базе данных имеет поле оценки, и значение этого поля определяет способ отображения строки со сведениями о композиции.</span><span class="sxs-lookup"><span data-stu-id="005be-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="005be-110">В следующем примере показано, как определить <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> для <xref:System.Windows.Controls.ListViewItem> объектов, представляющих песни в коллекции песен.</span><span class="sxs-lookup"><span data-stu-id="005be-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="005be-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> ссылается на <xref:System.Windows.Controls.ControlTemplate> объекты, которые определяют способ отображения строки сведений о песне.</span><span class="sxs-lookup"><span data-stu-id="005be-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="005be-112">В следующем примере показан <xref:System.Windows.Controls.ControlTemplate>, который добавляет текстовую строку `"Strongly Recommended"` в строку.</span><span class="sxs-lookup"><span data-stu-id="005be-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="005be-113">На этот шаблон имеется ссылка в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> и отображается, если рейтинг песни имеет значение 5 (пять).</span><span class="sxs-lookup"><span data-stu-id="005be-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="005be-114"><xref:System.Windows.Controls.ControlTemplate> включает объект <xref:System.Windows.Controls.GridViewRowPresenter>, который размещает содержимое строки в столбцах, как определено в режиме представления <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="005be-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="005be-115">В следующем примере определяется <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="005be-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="005be-116">См. также</span><span class="sxs-lookup"><span data-stu-id="005be-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="005be-117">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="005be-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="005be-118">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="005be-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="005be-119">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="005be-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
