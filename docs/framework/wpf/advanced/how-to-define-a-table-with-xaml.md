---
title: Практическое руководство. Определение таблицы с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 011f612527f0c9e89ec05643edbb95b2d908488c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776590"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="7f4e5-102">Практическое руководство. Определение таблицы с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="7f4e5-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="7f4e5-103">В следующем примере демонстрируется определение <xref:System.Windows.Documents.Table> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f4e5-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="7f4e5-104">Пример таблицы содержит четыре столбца (представленный <xref:System.Windows.Documents.TableColumn> элементов) и несколько строк (представленных <xref:System.Windows.Documents.TableRow> элементы) содержащий данные, а также как название, заголовок и нижний колонтитул сведения.</span><span class="sxs-lookup"><span data-stu-id="7f4e5-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="7f4e5-105">Строки, которые должны содержаться в <xref:System.Windows.Documents.TableRowGroup> элемент.</span><span class="sxs-lookup"><span data-stu-id="7f4e5-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="7f4e5-106">Каждая строка в таблице состоит из одной или нескольких ячеек (представленных <xref:System.Windows.Documents.TableCell> элементов).</span><span class="sxs-lookup"><span data-stu-id="7f4e5-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="7f4e5-107">Содержимое в ячейке таблицы должно содержаться в <xref:System.Windows.Documents.Block> элемент; в таком случае <xref:System.Windows.Documents.Paragraph> используются элементы.</span><span class="sxs-lookup"><span data-stu-id="7f4e5-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="7f4e5-108">Таблица также содержит гиперссылку (представленный <xref:System.Windows.Documents.Hyperlink> элемент) в строке нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="7f4e5-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f4e5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="7f4e5-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="7f4e5-110">На следующем рисунке показана отрисовка таблица, определенная в этом примере:</span><span class="sxs-lookup"><span data-stu-id="7f4e5-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![Снимок экрана: таблицы, определенной с помощью XAML.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
