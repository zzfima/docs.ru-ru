---
title: "Практическое руководство. Управление столбцами таблицы с помощью свойства столбцов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Columns - свойство"
  - "документы, работа со столбцами таблиц"
  - "свойства, Столбцы, работа со столбцами таблиц"
  - "таблицы, обработка столбцов"
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Управление столбцами таблицы с помощью свойства столбцов
В этом примере показаны некоторые из наиболее распространенных операций, которые могут выполняться со столбцами таблицы при помощи свойства <xref:System.Windows.Documents.Table.Columns%2A>.  
  
## Пример  
 В следующем пример создается новая таблица, а затем используется метод <xref:System.Windows.Documents.TableColumnCollection.Add%2A> для добавления столбцов в коллекцию <xref:System.Windows.Documents.Table.Columns%2A> таблицы.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## Пример  
 Следующий пример вставляет новый <xref:System.Windows.Documents.TableColumn>.  Новый столбец вставляется в позиции индекса 0, что делает его первым столбцом в таблице.  
  
> [!NOTE]
>  Коллекция <xref:System.Windows.Documents.TableColumnCollection> использует стандартную индексацию с нуля.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## Пример  
 Следующий пример получает доступ к некоторым произвольным свойствам в столбцах коллекции <xref:System.Windows.Documents.TableColumnCollection>, ссылаясь на определенные столбцы по индексу.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## Пример  
 Следующий пример получает число столбцов, в данный момент размещенных в таблице.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## Пример  
 Следующий пример удаляет определенный столбец по ссылке.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## Пример  
 Следующий пример удаляет определенный столбец по индексу.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## Пример  
 Следующий пример удаляет все столбцы из коллекции столбцов таблицы.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## См. также  
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [Определение таблицы с помощью XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [Построение таблицы программным способом](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Управление FlowDocument через свойство блоков](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)