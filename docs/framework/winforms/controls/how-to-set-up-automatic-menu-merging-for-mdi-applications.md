---
title: "Практическое руководство. Автоматическое слияние меню в приложениях MDI"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Практическое руководство. Автоматическое слияние меню в приложениях MDI
Ниже приведены основные шаги по настройке автоматического слияния в приложении многодокументного интерфейса (MDI) с <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Чтобы настроить автоматическое слияние меню  
  
1.  Создание родительской MDI-формы, установив его <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства `true`.  
  
2.  Добавить <xref:System.Windows.Forms.MenuStrip> для родительской формы MDI, установка его <xref:System.Windows.Forms.Form.MainMenuStrip%2A> свойства <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Создание дочерних MDI-формы и задание его <xref:System.Windows.Forms.Form.MdiParent%2A> на имя родительской формы.  
  
4.  Добавить <xref:System.Windows.Forms.MenuStrip> в дочерней форме MDI.  
  
5.  В дочерней форме задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство <xref:System.Windows.Forms.MenuStrip> для `false`.  
  
6.  Добавление пунктов меню дочерней формы <xref:System.Windows.Forms.MenuStrip> , которую требуется объединить в родительскую форму <xref:System.Windows.Forms.MenuStrip> при активации дочерней формы.  
  
7.  Используйте <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> свойства в меню элементы в дочерней формы <xref:System.Windows.Forms.MenuStrip> для управления слиянием в родительской формы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
