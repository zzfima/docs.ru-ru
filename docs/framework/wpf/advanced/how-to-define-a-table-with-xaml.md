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
# <a name="how-to-define-a-table-with-xaml"></a>Практическое руководство. Определение таблицы с помощью XAML
В следующем примере демонстрируется определение <xref:System.Windows.Documents.Table> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Пример таблицы содержит четыре столбца (представленный <xref:System.Windows.Documents.TableColumn> элементов) и несколько строк (представленных <xref:System.Windows.Documents.TableRow> элементы) содержащий данные, а также как название, заголовок и нижний колонтитул сведения.  Строки, которые должны содержаться в <xref:System.Windows.Documents.TableRowGroup> элемент.  Каждая строка в таблице состоит из одной или нескольких ячеек (представленных <xref:System.Windows.Documents.TableCell> элементов).  Содержимое в ячейке таблицы должно содержаться в <xref:System.Windows.Documents.Block> элемент; в таком случае <xref:System.Windows.Documents.Paragraph> используются элементы.  Таблица также содержит гиперссылку (представленный <xref:System.Windows.Documents.Hyperlink> элемент) в строке нижнего колонтитула.  
  
## <a name="example"></a>Пример  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 На следующем рисунке показана отрисовка таблица, определенная в этом примере:  
  
 ![Снимок экрана: таблицы, определенной с помощью XAML.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
