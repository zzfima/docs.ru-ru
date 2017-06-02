---
title: "Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "отображение дополнительных кнопок, MenuStrip - элемент управления [Windows Forms]"
  - "MenuStrip - элемент управления [Windows Forms], отображение дополнительных кнопок"
  - "дополнительные кнопки [Windows Forms], отображение в MenuStrip"
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)
Переключатели подобны флажкам за тем исключением, что одновременно может выбрать только один из них.  По умолчанию в классе <xref:System.Windows.Forms.ToolStripMenuItem> не реализована функциональность переключателей, однако в нем предусмотрена функциональность для создания флажков, на основе которой можно реализовать функциональность переключателей для пунктов меню в составе элемента управления <xref:System.Windows.Forms.MenuStrip>.  
  
 Если свойство <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> пункта меню имеет значение `true`, пользователь может устанавливать или снимать флажок рядом с пунктом меню щелчком мыши.  Свойство <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> показывает текущее состояние пункта меню.  Для реализации базовой функциональности переключателей необходимо при выборе нового пункта меню присваивать свойству <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> ранее выбранного пункта значение `false`.  
  
 Следующие процедуры описывают реализацию этой и дополнительной функциональности в классе, наследуемом от класса <xref:System.Windows.Forms.ToolStripMenuItem>.  Для обеспечения надлежащего поведения и внешнего вида переключателей в классе `ToolStripRadioButtonMenuItem` переопределяются такие члены, как <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> и <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>.  Кроме того, в данном классе переопределяется свойство <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> с тем, чтобы пункты подменю были отключены, если не выбран родительский элемент  
  
### Реализация поведения переключателей  
  
1.  Присвойте свойству <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> значение `true`, чтобы сделать возможным выделение пунктов меню.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> для снятия выделения с ранее выбранного пункта при выборе нового.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> так, чтобы при щелчке по уже выбранному пункту выделение не снималось.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### Изменение внешнего вида переключателей  
  
1.  Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, чтобы заменить стандартный флажок переключателем с помощью класса <xref:System.Windows.Forms.RadioButtonRenderer>.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Переопределите методы <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> и <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A>, чтобы отслеживать состояние мыши, и обеспечьте правильное отображение состояния переключателя методом <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### Отключение пунктов подменю, если не выбран родительский элемент  
  
1.  Переопределите свойство <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> так, чтобы пункт был отключен, если свойство <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> родительского элемента имеет значение `true`, а свойство <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> имеет значение `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>, чтобы подписаться на событие <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> родительского элемента.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  В обработчике события <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> родительского элемента необходимо объявить элемент недействительным, чтобы он отображался как включенный.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## Пример  
 В следующем примере кода приводится полное описание класса `ToolStripRadioButtonMenuItem`, а также классов <xref:System.Windows.Forms.Form> и `Program` для демонстрации поведения переключателей.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RadioButtonRenderer>   
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)