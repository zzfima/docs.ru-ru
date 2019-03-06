---
title: Практическое руководство. Управление столбцами и строками с помощью коллекций ColumnDefinitionsCollections и RowDefinitionsCollections
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: c3308f99b8d959b7513c5657d568a18959302aba
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360566"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a>Практическое руководство. Управление столбцами и строками с помощью коллекций ColumnDefinitionsCollections и RowDefinitionsCollections
В этом примере показано, как использовать методы в <xref:System.Windows.Controls.ColumnDefinitionCollection> и <xref:System.Windows.Controls.RowDefinitionCollection> классы для выполнения действий, таких как добавление, удаление или подсчет строк или столбцов содержимого. Например, вы можете <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, или <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> элементы, которые включены в <xref:System.Windows.Controls.ColumnDefinition> или <xref:System.Windows.Controls.RowDefinition>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Windows.Controls.Grid> элемент с <xref:System.Windows.FrameworkElement.Name%2A> из `grid1`. <xref:System.Windows.Controls.Grid> Содержит <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Controls.Button> элементы, управляющие различными методами коллекции. При нажатии кнопки <xref:System.Windows.Controls.Button>, она активирует вызов метода в файле кода.  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 В этом примере определяется ряд пользовательских методов, каждый соответствующий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл. Можно изменить число столбцов и строк в <xref:System.Windows.Controls.Grid> несколькими способами, включая добавление или удаление строк и столбцов; и подсчета общего количества строк и столбцов. Чтобы предотвратить <xref:System.ArgumentOutOfRangeException> и <xref:System.ArgumentException> исключения, можно использовать функцию проверки ошибок, <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> предоставляет метод.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
