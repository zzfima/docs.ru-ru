---
title: Общие сведения об элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: a54223c45c7e896676a9b27274bb8feb4acd27e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568533"
---
# <a name="tablelayoutpanel-control-overview"></a>Общие сведения об элементе управления TableLayoutPanel
Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> упорядочивает содержимое в сетке. Так как макет строится как во время разработки, так и во время выполнения, его можно изменять динамически по мере изменения среды приложения. Это позволяет пропорционально изменять размер элементов управления на панели с учетом изменений, например изменения размера родительского элемента управления или изменения длина текста в результате локализации.  
  
 Любой элемент управления Windows Forms, включая другие экземпляры <xref:System.Windows.Forms.TableLayoutPanel>, может быть дочерним относительно элемента <xref:System.Windows.Forms.TableLayoutPanel>. Это позволяет создавать сложные макеты, динамически меняющиеся во время выполнения.  
  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> может расширяться для размещения новых элементов управления при их добавлении в зависимости от значений свойств <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> и <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>. Значение 0 свойства <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> или <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> указывает на то, что элемент <xref:System.Windows.Forms.TableLayoutPanel> не будет ограничиваться в соответствующем направлении.  
  
 Также можно управлять направлением расширения элемента управления <xref:System.Windows.Forms.TableLayoutPanel> (горизонтальное или вертикальное) после его заполнения дочерними элементами управления. По умолчанию элемент управления <xref:System.Windows.Forms.TableLayoutPanel> расширяется вниз путем добавления строк.  
  
 Если необходимо изменить поведение строк и столбцов, заданное по умолчанию, используйте свойства <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> и <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>. Свойства строк и столбцов можно задавать по отдельности.  
  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> добавляет следующие свойства в свои дочерние элементы управления: `Cell`, `Column`, `Row`, `ColumnSpan` и `RowSpan`.  
  
 Чтобы объединить ячейки в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>, установите свойство `ColumnSpan` или `RowSpan` дочернего элемента управления.  
  
1.  [Практическое руководство. Выравнивание и Растягивание элемента управления в элементе управления TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3.  [Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4.  [Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutSettings>
- [Практическое руководство. Разработка макета формы Windows, с учетом будущей локализации](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Практическое руководство. Создание переменного размера Windows формы для ввода данных](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)
- [Советы по использованию элемента управления TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
