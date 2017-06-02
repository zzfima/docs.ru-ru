---
title: "Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора | Microsoft Docs"
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
  - "ImageList - компонент [Windows Forms], добавление изображений"
  - "ImageList - компонент [Windows Forms], удаление изображений"
  - "изображения [Windows Forms], добавление в компонент ImageList"
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Добавление и удаление изображений из компонента ImageList с помощью конструктора
Можно добавлять рисунки в компонент <xref:System.Windows.Forms.ImageList> несколькими способами.  Можно быстро добавлять рисунки с помощью смарт\-тега, связанного с <xref:System.Windows.Forms.ImageList>; при установке нескольких других свойств для <xref:System.Windows.Forms.ImageList> удобнее добавлять рисунки с помощью окна свойств.  Также можно добавлять рисунки с помощью кода.  Дополнительные сведения о добавлении рисунков с помощью кода см. в разделе [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  Компонент <xref:System.Windows.Forms.ImageList> обычно заполняется рисунками перед связыванием с каким\-либо элементом управления, но это не обязательно.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Для добавления и удаления рисунков с помощью окна свойств выполните следующие действия.  
  
1.  Выберите компонент <xref:System.Windows.Forms.ImageList> или добавьте его в форму.  
  
2.  В окне "Свойства" нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.ImageList.Images%2A>.  
  
3.  В окне **редактора коллекции рисунков** нажмите кнопку **Добавить** или **Удалить** для добавления рисунков в список или удаления их из него.  
  
### Для добавления и удаления рисунков с помощью смарт\-тега выполните следующие действия.  
  
1.  Выберите компонент <xref:System.Windows.Forms.ImageList> или добавьте его в форму.  
  
2.  Щелкните значок смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)  
  
3.  В диалоговом окне **Задачи списка рисунков** выберите **Выбрать рисунки**.  
  
4.  В окне **редактора коллекции рисунков**  нажмите кнопку **Добавить** или **Удалить** для добавления рисунков в список или удаления их из него.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Пошаговое руководство. Выполнение типичных задач с помощью смарт\-тегов в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)   
 [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)