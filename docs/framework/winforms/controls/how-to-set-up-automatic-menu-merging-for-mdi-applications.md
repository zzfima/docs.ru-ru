---
title: Практическое руководство. Задайте автоматическое слияние меню приложениях MDI
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 152db39e7c947d5a49eaed81b00d13c02aa8014c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719739"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Практическое руководство. Задайте автоматическое слияние меню приложениях MDI
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
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
