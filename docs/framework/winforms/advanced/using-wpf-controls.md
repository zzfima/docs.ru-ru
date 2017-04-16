---
title: "Использование элементов управления WPF | Microsoft Docs"
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
  - "взаимодействие [WPF]"
  - "конструктор Windows Forms, взаимодействие с WPF"
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Использование элементов управления WPF
Можно использовать элементы управления Windows Presentation Foundation \(WPF\) в приложениях на основе Windows Forms.  Это две различные технологии, но они отлично взаимодействуют.  
  
 Конструктор Windows Forms предоставляет наглядную среду проектирования для размещения элементов управления Windows Presentation Foundation.  Элементы управления WPF размещаются элементом управления Windows Forms под названием <xref:System.Windows.Forms.Integration.ElementHost>.  Этот элемент управления позволяет использовать элемент управления WPF в форме и получать сообщения от клавиатуры и мыши.  Во время разработки можно располагать в форме элемент управления <xref:System.Windows.Forms.Integration.ElementHost> точно так же, как любой другой элементы управления Windows Forms.  
  
 Можно также использовать элементы управления Windows Forms в приложениях WPF.  Дополнительные сведения см. в разделе [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26).  
  
## В этом подразделе  
 [Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Как скопировать элемент управления WPF в форму Windows Forms.  
  
 [Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Как использовать функции проектирования форм Windows Forms, такие как линии привязки, для размещения элементов управления WPF.  
  
 [Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Отображает схему работы между конструктором Windows Forms и [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] при изменении свойств элементов управления WPF.  
  
 [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Демонстрируется способ создания элемента управления Windows Presentation Foundation для использования в приложениях Windows.  
  
 [Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Как скопировать элемент управления WPF из одной формы Windows Forms в другую.  
  
 [Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Как скопировать выбрать нужные типы элементов управления WPF для отображения в форме.  
  
 [Пошаговое руководство. Применение стилей к содержимому WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Отображает схему работы между конструктором Windows Forms и [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] для применения стилей к элементам управления WPF.  
  
## Ссылка  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Описание класса, который можно использовать для размещения элементов управления Windows Presentation Foundation в приложениях на основе Windows Forms.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Описание класса, который можно использовать для размещения элементов управления Windows Forms в приложениях на основе Windows Presentation Foundation.  
  
## Связанные подразделы  
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Описывает взаимодействие между технологиями WPF и формы Windows Forms.  
  
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)  
 Описание способа создания элементов управления Windows Presentation Foundation в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].