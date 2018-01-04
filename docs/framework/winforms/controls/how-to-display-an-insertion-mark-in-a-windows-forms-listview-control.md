---
title: "Практическое руководство. Индикация места вставки в элементе управления ListView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff59a7b716944779fd5c87b58034eb60d5981b02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a>Практическое руководство. Индикация места вставки в элементе управления ListView в Windows Forms
Метка вставки в элементе управления <xref:System.Windows.Forms.ListView> показывает пользователю, куда будут помещены перетаскиваемые элементы. Когда пользователь перетаскивает элемент на точку между двумя другими элементами, метка вставки показывает ожидаемое новое расположение элемента.  
  
> [!NOTE]
>  Функция метки вставки доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. В предыдущих версиях операционных систем код, связанный с меткой вставки, не действует и метка вставки не отображается. Для получения дополнительной информации см. <xref:System.Windows.Forms.ListViewInsertionMark>.  
  
 На рисунке ниже показана метка вставки.  
  
 ![Маркер вставки ListView](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")  
  
 В примере кода ниже показано, как использовать эту возможность.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms;  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewInsertionMark>  
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Возможности Windows XP и элементы управления Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Пример. Выполнение операции перетаскивания в Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
