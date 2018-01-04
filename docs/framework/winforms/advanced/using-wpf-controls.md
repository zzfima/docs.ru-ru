---
title: "Использование элементов управления WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c14da85b377b3ef80d6accbc8b0319959a75bcd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-wpf-controls"></a>Использование элементов управления WPF
Элементы управления Windows Presentation Foundation (WPF) можно использовать в приложениях Windows Forms. Хотя эти две различные технологии, они взаимодействуют.  
  
 Конструктор Windows Forms предоставляет визуальную среду проектирования для размещения элементов управления Windows Presentation Foundation. Элемент управления WPF размещается специальных элементов управления Windows Forms с именем <xref:System.Windows.Forms.Integration.ElementHost>. Этот элемент управления позволяет участвовать в макет формы и получать сообщения клавиатуры и мыши элемента управления WPF. Во время разработки, вы можете упорядочить <xref:System.Windows.Forms.Integration.ElementHost> управления так же, как и любой элемент управления Windows Forms.  
  
 Можно также использовать элементы управления Windows Forms в приложениях WPF. Дополнительные сведения см. в разделе [конструктор WPF](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Показано, как скопировать элемент управления Windows Presentation Foundation в Windows Forms.  
  
 [Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Показано, как использовать функции структуры Windows Forms, такие как закрепление и линии привязки, для размещения элементов управления Windows Presentation Foundation.  
  
 [Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Показан рабочий процесс между конструктор Windows Forms и [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] по изменению свойств для элементов управления WPF.  
  
 [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Показано, как создать элемент управления Windows Presentation Foundation для использования в приложениях Windows Forms.  
  
 [Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Показано, как скопировать элемент управления Windows Presentation Foundation из одной формы Windows Forms в другую.  
  
 [Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Показано, как выбрать типы элементов управления Windows Presentation Foundation, который будет отображаться в форме.  
  
 [Пошаговое руководство. Применение стилей к содержимому WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Показан рабочий процесс между конструктор Windows Forms и [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] применения стилей к элементам управления Windows Presentation Foundation.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Описывает класс, который можно использовать в приложениях Windows Forms для размещения элементов управления Windows Presentation Foundation.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Описывает класс, который можно использовать для размещения элементов управления Windows Forms в приложении Windows Presentation Foundation.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Описывает взаимодействие между технологиями Windows Presentation Foundation и Windows Forms.  
  
 [Конструктор WPF](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 Инструкции по разработке элементов управления Windows Presentation Foundation в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].
