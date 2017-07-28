---
title: "Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "дочерние элементы управления, привязка и закрепление"
  - "элементы управления [Windows Forms], дочерний"
  - "макет [Windows Forms], дочерние элементы управления"
  - "TableLayoutPanel - элемент управления [Windows Forms], дочерние элементы управления"
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel
Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> поддерживает свойства <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> в своих дочерних элементах управления.  
  
### Выравнивание дочернего элемента управления в ячейке TableLayoutPanel  
  
1.  Создайте элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в форме.  
  
2.  Присвойте свойствам <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> и <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> элемента управления <xref:System.Windows.Forms.TableLayoutPanel> значение 1.  
  
3.  Создайте элемент управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.  Элемент <xref:System.Windows.Forms.Button> расположен в левом верхнем углу ячейки.  
  
4.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на `Left`.  Элемент управления <xref:System.Windows.Forms.Button> выровняется по левому краю ячейки.  
  
    > [!NOTE]
    >  Такое поведение отличается от поведения других контейнерных элементов управления.  Когда свойству <xref:System.Windows.Forms.Control.Anchor%2A> присваивается значение<xref:System.Windows.Forms.Control.Anchor%2A>, дочерние элементы управления других контейнерных элементов управления не перемещаются, а расстояние между закрепленным элементом управления и границей родительского контейнера фиксируется.  
  
5.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на `Top, Left`.  Элемент управления <xref:System.Windows.Forms.Button> займет левый верхний угол ячейки.  
  
6.  Повторите шаг 5 со значением `Top, Right`, чтобы переместить элемент управления <xref:System.Windows.Forms.Button> в правый верхний угол ячейки.  Повторите то же самое, используя значения `Bottom, Left` и `Bottom, Right`.  
  
### Растяжение дочернего элемента управления в ячейке TableLayoutPanel  
  
1.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на `Left, Right`.  Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он растянется по ширине ячейки.  
  
    > [!NOTE]
    >  Такое поведение отличается от поведения других контейнерных элементов управления.  Размеры дочерних элементов управления других контейнерных элементов не изменяются, когда свойству <xref:System.Windows.Forms.Control.Anchor%2A> присваивается значение `Left, Right` или `Top, Bottom`.  
  
2.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на `Top, Bottom`.  Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он растянется по высоте ячейки.  
  
3.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на `Top, Bottom, Left, Right`.  Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он заполнит ячейку.  
  
4.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на `None`.  Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он расположится по центру ячейки.  
  
5.  Измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления <xref:System.Windows.Forms.Button> на <xref:System.Windows.Forms.DockStyle>.  Элемент управления <xref:System.Windows.Forms.Button> выровняется по левому краю ячейки.  Ширина элемента управления <xref:System.Windows.Forms.Button> сохранится, а высота изменится для заполнения ячейки по вертикали.  
  
    > [!NOTE]
    >  Другие контейнерные элементы управления обладают аналогичным поведением.  
  
6.  Измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления <xref:System.Windows.Forms.Button> на <xref:System.Windows.Forms.DockStyle>.  Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он заполнит ячейку.  
  
## Пример  
 На рисунке ниже показаны пять кнопок, прикрепленных в пяти отдельных ячейках <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Закрепление TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.png "VS\_TLPanchor")  
  
 На рисунке ниже показаны четыре кнопки, прикрепленные в углах четырех отдельных ячеек <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Закрепление TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.png "VS\_TLPanchor2")  
  
 На рисунке ниже показаны три кнопки, растянутые в результате прикрепления в трех отдельных ячейках <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 ![Закрепление TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.png "VS\_TLPAnchor3")  
  
 В примере кода ниже демонстрируются все сочетания значений свойств <xref:System.Windows.Forms.Control.Anchor%2A>, используемые для размещения элемента управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Элемент управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)