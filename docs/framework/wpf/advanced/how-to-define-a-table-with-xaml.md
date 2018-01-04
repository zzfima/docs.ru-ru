---
title: "Практическое руководство. Определение таблицы с помощью XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b932c7df822edabc5626f20af2bfc1eb3a7f93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a>Практическое руководство. Определение таблицы с помощью XAML
В следующем примере демонстрируется определение <xref:System.Windows.Documents.Table> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Пример таблицы содержит четыре столбца (представленного <xref:System.Windows.Documents.TableColumn> элементы) и несколько строк (представленного <xref:System.Windows.Documents.TableRow> элементов) с данными также как название, заголовок и нижний колонтитул сведения.  Строки, которые должны содержаться в <xref:System.Windows.Documents.TableRowGroup> элемент.  Каждая строка в таблице состоит из одной или нескольких ячеек (представленного <xref:System.Windows.Documents.TableCell> элементов).  Содержимое в ячейку таблицы, которые должны содержаться в <xref:System.Windows.Documents.Block> элемент; в этом случае <xref:System.Windows.Documents.Paragraph> используются элементы.  Таблица также содержит гиперссылку (представленного <xref:System.Windows.Documents.Hyperlink> элемент) в строке нижнего колонтитула.  
  
## <a name="example"></a>Пример  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 На следующем рисунке показано, как отображается таблица, определенная в этом примере.  
  
 ![Отображаемая таблица.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
