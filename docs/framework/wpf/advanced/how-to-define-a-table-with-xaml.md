---
title: Практическое руководство. Определение таблицы с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 2a35a27567d962fc125cb3c408ccab95afa222af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543105"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="978a1-102">Практическое руководство. Определение таблицы с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="978a1-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="978a1-103">В следующем примере демонстрируется определение <xref:System.Windows.Documents.Table> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="978a1-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="978a1-104">Пример таблицы содержит четыре столбца (представленного <xref:System.Windows.Documents.TableColumn> элементы) и несколько строк (представленного <xref:System.Windows.Documents.TableRow> элементов) с данными также как название, заголовок и нижний колонтитул сведения.</span><span class="sxs-lookup"><span data-stu-id="978a1-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="978a1-105">Строки, которые должны содержаться в <xref:System.Windows.Documents.TableRowGroup> элемент.</span><span class="sxs-lookup"><span data-stu-id="978a1-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="978a1-106">Каждая строка в таблице состоит из одной или нескольких ячеек (представленного <xref:System.Windows.Documents.TableCell> элементов).</span><span class="sxs-lookup"><span data-stu-id="978a1-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="978a1-107">Содержимое в ячейку таблицы, которые должны содержаться в <xref:System.Windows.Documents.Block> элемент; в этом случае <xref:System.Windows.Documents.Paragraph> используются элементы.</span><span class="sxs-lookup"><span data-stu-id="978a1-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="978a1-108">Таблица также содержит гиперссылку (представленного <xref:System.Windows.Documents.Hyperlink> элемент) в строке нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="978a1-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="978a1-109">Пример</span><span class="sxs-lookup"><span data-stu-id="978a1-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="978a1-110">На следующем рисунке показано, как отображается таблица, определенная в этом примере.</span><span class="sxs-lookup"><span data-stu-id="978a1-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="978a1-111">![Отображаемая таблица.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="978a1-111">![Rendered table.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span></span>
