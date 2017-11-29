---
title: "Практическое руководство. Управление столбцами и строками с помощью коллекций ColumnDefinitionsCollections и RowDefinitionsCollections"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e87c5001a676bcda331d289c286cf6b3e87c136f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="abe21-102">Практическое руководство. Управление столбцами и строками с помощью коллекций ColumnDefinitionsCollections и RowDefinitionsCollections</span><span class="sxs-lookup"><span data-stu-id="abe21-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="abe21-103">В этом примере показано, как использовать методы в <xref:System.Windows.Controls.ColumnDefinitionCollection> и <xref:System.Windows.Controls.RowDefinitionCollection> классы для выполнения действий, таких как добавление, удаление или подсчет содержимого строк или столбцов.</span><span class="sxs-lookup"><span data-stu-id="abe21-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="abe21-104">Например, вы можете <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, или <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> элементы, которые включены в <xref:System.Windows.Controls.ColumnDefinition> или <xref:System.Windows.Controls.RowDefinition>.</span><span class="sxs-lookup"><span data-stu-id="abe21-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abe21-105">Пример</span><span class="sxs-lookup"><span data-stu-id="abe21-105">Example</span></span>  
 <span data-ttu-id="abe21-106">В следующем примере создается <xref:System.Windows.Controls.Grid> элемент с <xref:System.Windows.FrameworkElement.Name%2A> из `grid1`.</span><span class="sxs-lookup"><span data-stu-id="abe21-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="abe21-107"><xref:System.Windows.Controls.Grid> Содержит <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Controls.Button> элементы, управляющие различными методами коллекции.</span><span class="sxs-lookup"><span data-stu-id="abe21-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="abe21-108">При нажатии кнопки <xref:System.Windows.Controls.Button>, он активируется вызов метода в файле кода.</span><span class="sxs-lookup"><span data-stu-id="abe21-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="abe21-109">Этот пример определяет набор пользовательских методов, каждый соответствующий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла.</span><span class="sxs-lookup"><span data-stu-id="abe21-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="abe21-110">Можно изменить число столбцов и строк в <xref:System.Windows.Controls.Grid> несколькими способами, включая добавление или удаление строк и столбцов; и подсчета общее число строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="abe21-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="abe21-111">Чтобы предотвратить <xref:System.ArgumentOutOfRangeException> и <xref:System.ArgumentException> исключения, можно использовать функцию проверки ошибок, <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> предоставляет метод.</span><span class="sxs-lookup"><span data-stu-id="abe21-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="abe21-112">См. также</span><span class="sxs-lookup"><span data-stu-id="abe21-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.ColumnDefinitionCollection>  
 <xref:System.Windows.Controls.RowDefinitionCollection>
