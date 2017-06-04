---
title: "Практическое руководство. Создание родительских MDI-форм | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI - интерфейс, создание форм"
  - "родительские формы"
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Создание родительских MDI-форм
> [!IMPORTANT]
>  В этом разделе используется элемент управления <xref:System.Windows.Forms.MainMenu>, который был заменен на элемент управления <xref:System.Windows.Forms.MenuStrip>.  Элемент управления <xref:System.Windows.Forms.MainMenu> сохраняется для обеспечения обратной совместимости и использования в будущем.  Подробнее о создании родительской формы MDI с помощью <xref:System.Windows.Forms.MenuStrip> см. в разделе [Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).  
  
 Базой для приложения многодокументного интерфейса \(MDI\) является родительская MDI\-форма.  Это форма, содержащая дочерние MDI\-окна, которые являются вложенными окнами, когда пользователи взаимодействуют с MDI\-приложением.  Создание родительской MDI\-формы представляет собой несложный процесс, как с помощью конструктора Windows Forms, так и на программном уровне.  
  
### Создание родительской MDI\-формы во время разработки  
  
1.  Создайте проект приложения Windows.  
  
2.  В окне **Properties** задайте для свойства [IsMDIContainer](frlrfSystemWindowsFormsFormClassIsMDIContainerTopic) значение **true**.  
  
     При этом форма назначается в качестве MDI\-контейнера для дочерних окон.  
  
    > [!NOTE]
    >  При необходимости, при настройке свойств в окне **Properties** для свойства `WindowState` также можно задать значение **Maximized**, так как управлять дочерними MDI\-окнами проще, когда родительская форма развернута.  Кроме того, следует помнить, что граница родительской MDI\-формы будет окрашена в системный цвет \(заданный на панели управления Windows\), а не в черный цвет, заданный с помощью свойства <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=fullName>.  
  
3.  Перетащите из области **Панель элементов** элемент управления **MenuStrip** в форму.  Создайте пункт меню верхнего уровня — для свойства **Text** задайте значение **&File**, пункты меню должны называться **&New** и **&Close**.  Также создайте пункт меню верхнего уровня **&Window**.  
  
     Первое меню будет создавать и скрывать пункты меню во время выполнения, а второе меню будет отслеживать открытые дочерние MDI\-окна.  На этом этапе вы создали родительское MDI\-окно.  
  
4.  Нажмите клавишу **F5**, чтобы запустить приложение.  Подробнее о создании дочерних MDI\-окон, работающих в родительской MDI\-форме, см. в разделе [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
  
## См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Практическое руководство. Определение активной дочерней MDI\-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Практическое руководство. Отправка данных в активную дочернюю MDI\-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)