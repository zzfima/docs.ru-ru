---
title: Практическое руководство. Определение таблицы с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 7398af6fddae56238e1af3ee4e726420c01ab7ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376940"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="23e58-102">Практическое руководство. Определение таблицы с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="23e58-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="23e58-103">В следующем примере демонстрируется определение <xref:System.Windows.Documents.Table> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23e58-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="23e58-104">Пример таблицы содержит четыре столбца (представленный <xref:System.Windows.Documents.TableColumn> элементов) и несколько строк (представленных <xref:System.Windows.Documents.TableRow> элементы) содержащий данные, а также как название, заголовок и нижний колонтитул сведения.</span><span class="sxs-lookup"><span data-stu-id="23e58-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="23e58-105">Строки, которые должны содержаться в <xref:System.Windows.Documents.TableRowGroup> элемент.</span><span class="sxs-lookup"><span data-stu-id="23e58-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="23e58-106">Каждая строка в таблице состоит из одной или нескольких ячеек (представленных <xref:System.Windows.Documents.TableCell> элементов).</span><span class="sxs-lookup"><span data-stu-id="23e58-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="23e58-107">Содержимое в ячейке таблицы должно содержаться в <xref:System.Windows.Documents.Block> элемент; в таком случае <xref:System.Windows.Documents.Paragraph> используются элементы.</span><span class="sxs-lookup"><span data-stu-id="23e58-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="23e58-108">Таблица также содержит гиперссылку (представленный <xref:System.Windows.Documents.Hyperlink> элемент) в строке нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="23e58-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23e58-109">Пример</span><span class="sxs-lookup"><span data-stu-id="23e58-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="23e58-110">На следующем рисунке показано, как отображается таблица, определенная в этом примере.</span><span class="sxs-lookup"><span data-stu-id="23e58-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="23e58-111">![Отображаемая таблица.](./media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="23e58-111">![Rendered table.](./media/tableeg.png "TableEG")</span></span>
