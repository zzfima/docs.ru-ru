---
title: "Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)"
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
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15f2d1492148a4b00a4b96844f546a4dc968eef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)
Переключатели, также известные как переключатели, похожи на флажки, за исключением того, пользователи могут выбрать только один раз. Несмотря на то что по умолчанию <xref:System.Windows.Forms.ToolStripMenuItem> класс не предоставляет функциональность переключателей, класс предоставляет поведение флажков, которые можно настроить для реализации поведения переключателей для пунктов меню в <xref:System.Windows.Forms.MenuStrip> элемента управления.  
  
 Когда <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойство пункта меню `true`, пользователям можно щелкнуть элемент, чтобы показать или скрыть метку. <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Свойство указывает текущее состояние элемента. Для реализации поведения основные переключатель, вы должны убедиться, что при выборе элемента <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свойство ранее выбранного элемента в `false`.  
  
 Следующие процедуры описывают, как это реализовать и дополнительные функциональные возможности в наследуемом классе <xref:System.Windows.Forms.ToolStripMenuItem> класса. `ToolStripRadioButtonMenuItem` Класс переопределяет элементы, такие как <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> и <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> для предоставления выбора поведение и внешний вид кнопки. Кроме того, этот класс переопределяет <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство, параметры, в подменю отключены, если не выбран родительский элемент.  
  
### <a name="to-implement-option-button-selection-behavior"></a>Для реализации поведения выбора переключателей  
  
1.  Инициализация <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойства `true` Включение выбора элемента.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> метод, чтобы удалить выбор ранее выбранного элемента, если элемент выбран.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> метод, чтобы при щелчке элемента, который уже был выбран не будет снять выделение.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>Чтобы изменить внешний вид элементов переключателей  
  
1.  Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> метод, чтобы заменить флажок по умолчанию с помощью переключателя <xref:System.Windows.Forms.RadioButtonRenderer> класса.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, и <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> методы для отслеживания состояния мыши и убедитесь, что <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> метод закрашивает состояния правильный переключателя.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Отключение пунктов подменю, если не выбран родительский элемент  
  
1.  Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства, чтобы элемент остается недоступной, если он имеет родительский элемент с обоими <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> значение `true` и <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> значение `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> метод подписаться на <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> событие родительского элемента.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  В обработчике родительского элемента <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> события, сделайте элемент для обновления экрана с новым состоянием включено.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода предоставляет полное `ToolStripRadioButtonMenuItem` класса и <xref:System.Windows.Forms.Form> класса и `Program` для демонстрации поведения переключателей.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
