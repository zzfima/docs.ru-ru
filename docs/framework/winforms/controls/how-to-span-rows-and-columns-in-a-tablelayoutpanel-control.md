---
title: Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a78286be8ef64212d945b3cb11a2963d5a1b2e79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535351"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
Элементы управления в <xref:System.Windows.Forms.TableLayoutPanel> элемент управления может занимать смежных строк и столбцов.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-span-columns-and-rows"></a>Чтобы объединить столбцы и строки  
  
1.  Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.  
  
2.  Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в левый верхний угол элемента <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.  
  
3.  Задать <xref:System.Windows.Forms.Button> элемента управления **ColumnSpan** свойства **2**. Обратите внимание, что <xref:System.Windows.Forms.Button> управления охватывает первый и второй столбцы.  
  
4.  Задать <xref:System.Windows.Forms.Button> элемента управления **RowSpan** свойства **2**. Обратите внимание, что <xref:System.Windows.Forms.Button> управления охватывает первую и вторую строку.  
  
5.  Задать <xref:System.Windows.Forms.Button> элемента управления **ColumnSpan** свойства **1**. Обратите внимание, что <xref:System.Windows.Forms.Button> управления перемещается в первый столбец, но охватывает первую и вторую строку.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
