---
title: "Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения"
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
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8185adbf7d8979f03b3d0428fcc2ec0941c7999f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения
Настройка внешнего вида элементов управления <xref:System.Windows.Forms.ToolStrip> может производиться отдельно для каждого из них или для всех элементов управления <xref:System.Windows.Forms.ToolStrip>, используемых в приложении.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как выборочно применить пользовательское средство отрисовки к элементу управления <xref:System.Windows.Forms.ToolStrip> и элементу управления <xref:System.Windows.Forms.MenuStrip>.  
  
 Чтобы использовать этот пример, скомпилируйте и запустите приложение, а затем выберите область пользовательской отрисовки в элементе управления <xref:System.Windows.Forms.ComboBox>. Нажмите **Применить**, чтобы задать средство отрисовки.  
  
 Чтобы увидеть пользовательскую отрисовку элемента меню, выберите <xref:System.Windows.Forms.MenuStrip> параметр из <xref:System.Windows.Forms.ComboBox> управлять, щелкните **применить**, а затем откройте **файл** пункта меню.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Чтобы применить пользовательское средство отрисовки ко всем элементам управления <xref:System.Windows.Forms.ToolStrip>, используемым в приложении, задайте свойство <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>.  
  
 Чтобы применить пользовательское средство отрисовки к отдельному элементу управления <xref:System.Windows.Forms.ToolStrip>, задайте свойство <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
