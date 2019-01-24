---
title: Как выполнить Задайте автоматическое слияние меню приложениях MDI
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 3aeaf9ee4818b6689905c10d2bd46fc887609c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549828"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Как выполнить Задайте автоматическое слияние меню приложениях MDI
В следующей процедуре представлены основные шаги по настройке автоматического слияния в приложении многодокументного интерфейса (MDI) с <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Чтобы задать автоматическое слияние меню  
  
1.  Создание родительской MDI-формы, задав его <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства `true`.  
  
2.  Добавить <xref:System.Windows.Forms.MenuStrip> для родительской формы MDI, установка его <xref:System.Windows.Forms.Form.MainMenuStrip%2A> свойства <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Создание дочерних MDI-формы и задание его <xref:System.Windows.Forms.Form.MdiParent%2A> имя родительской формы.  
  
4.  Добавление <xref:System.Windows.Forms.MenuStrip> для дочерней формы MDI.  
  
5.  На дочерней формы, задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство <xref:System.Windows.Forms.MenuStrip> для `false`.  
  
6.  Добавление элементов меню в форме дочерних <xref:System.Windows.Forms.MenuStrip> , которые необходимо объединить в родительской формы <xref:System.Windows.Forms.MenuStrip> при активации дочерней формы.  
  
7.  Используйте <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> свойства в меню элементов в форме дочерних <xref:System.Windows.Forms.MenuStrip> для управления слиянием в родительской формы.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
