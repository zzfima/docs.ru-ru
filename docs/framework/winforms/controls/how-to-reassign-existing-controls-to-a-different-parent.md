---
title: Как выполнить Переназначение существующих элементов управления другим родительским
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: fa1bd6c0274fdf702072e062e6eeab7078375491
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600288"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Как выполнить Переназначение существующих элементов управления другим родительским
Можно назначать существующие в форме элементы управления новому контейнерному элементу управления.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>Переназначение существующих элементов управления другим родительским элементам  
  
1.  Перетащите три элемента управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму.  
  
     Расположите их рядом друг с другом, но не выравнивайте.  
  
2.  В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
     Не перетаскивайте значок на форму.  
  
3.  Переместите указатель мыши к трем элементам управления <xref:System.Windows.Forms.Button> .  
  
     Указатель превратится в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
4.  Нажмите и удерживайте кнопку мыши.  
  
5.  Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
6.  Обведите таким образом три элемента управления <xref:System.Windows.Forms.Button> .  
  
7.  Отпустите кнопку мыши.  
  
     Теперь три элемента управления <xref:System.Windows.Forms.Button> вставлены в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Упорядочение элементов управления в формах Windows Forms, с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
