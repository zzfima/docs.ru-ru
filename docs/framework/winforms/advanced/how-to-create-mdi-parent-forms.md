---
title: "Практическое руководство. Создание родительских MDI-форм"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f768e01981f75e5e322fd984e73ccf7b185c5e20
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-mdi-parent-forms"></a>Практическое руководство. Создание родительских MDI-форм
> [!IMPORTANT]
>  В этом разделе используется элемент управления <xref:System.Windows.Forms.MainMenu>, который был заменен на элемент управления <xref:System.Windows.Forms.MenuStrip>. Элемент управления <xref:System.Windows.Forms.MainMenu> сохраняется для обеспечения обратной совместимости и использования в будущем.  Дополнительные сведения о создании MDI родительской формы с помощью <xref:System.Windows.Forms.MenuStrip>, в разделе [как: Создание списка в окне MDI с помощью MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).  
  
 Базой для приложения многодокументного интерфейса (MDI) является родительская MDI-форма. Это форма, содержащая дочерние MDI-окна, которые являются вложенными окнами, когда пользователи взаимодействуют с MDI-приложением. Создание родительской MDI-формы представляет собой несложный процесс, как с помощью конструктора Windows Forms, так и на программном уровне.  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a>Создание родительской MDI-формы во время разработки  
  
1.  Создайте проект приложения Windows.  
  
2.  В **свойства** задайте <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства **true**.  
  
     При этом форма назначается в качестве MDI-контейнера для дочерних окон.  
  
    > [!NOTE]
    >  При необходимости, при настройке свойств в окне **Свойства** для свойства `WindowState` также можно задать значение **Maximized**, так как управлять дочерними MDI-окнами проще, когда родительская форма развернута. Кроме того, следует помнить, что граница родительской MDI-формы будет окрашена в системный цвет (заданный на панели управления Windows), а не в черный цвет, заданный с помощью свойства <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.  
  
3.  Перетащите элемент управления **MenuStrip** из **панели элементов** в форму. Создайте пункт меню верхнего уровня — для свойства **Text** задайте значение **&File**, пункты меню должны называться **&New** и **&Close**. Также создайте пункт меню верхнего уровня **&Window**.  
  
     Первое меню будет создавать и скрывать пункты меню во время выполнения, а второе меню будет отслеживать открытые дочерние MDI-окна. На этом этапе вы создали родительское MDI-окно.  
  
4.  Нажмите клавишу **F5** для запуска приложения. Подробнее о создании дочерних MDI-окон, работающих в родительской MDI-форме, см. в разделе [Практическое руководство. Создание дочерних MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).  
  
## <a name="see-also"></a>См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Практическое руководство. Создание дочерних MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Практическое руководство. Определение активной дочерней MDI-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [Практическое руководство. Отправка данных в активную дочернюю MDI-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
