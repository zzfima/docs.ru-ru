---
title: "Основы разработки элементов управления форм Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca2bac983e25ab7453230a6718fe7eaa98e82275
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-control-development-basics"></a>Основы разработки элементов управления форм Windows Forms
Элемент управления Windows Forms — это класс, производный прямо или косвенно от <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Ниже описаны распространенные сценарии для разработки элементов управления Windows Forms.  
  
-   Объединение существующих элементов управления для создания составного элемента управления.  
  
     Составные элементы управления инкапсулируют пользовательский интерфейс, который можно использовать как элемент управления. Пример составного элемента управления — элемент управления, который состоит из текстового поля и кнопки сброса. Визуальные конструкторы предлагают широкие возможности поддержки создания составных элементов управления. Для создания составного элемента управления, производный от <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает клавиатурную маршрутизацию для дочерних элементов управления и позволяет им работать в группе. Дополнительные сведения см. в разделе [Разработка составного элемента Windows Forms](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Расширение существующего элемента управления для его настройки или для добавления новых функций.  
  
     Не может изменяться, цвет кнопки и кнопки, которая имеет дополнительное свойство, которое отслеживает, сколько раз была нажата являются примерами расширенных элементов управления. Любой элемент управления Windows Forms можно настроить путем создания класса, производного от него и переопределения или добавления свойств, методов и событий.  
  
-   Создание элемента управления, который объединяет и не расширяет существующие элементы управления.  
  
     В этом случае элемент управления следует наследовать от базового класса <xref:System.Windows.Forms.Control>. Можно добавить также а переопределять свойства, методы и события базового класса. Чтобы приступить к работе, см. [как: разработка простого элемента управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 Базовый класс для элементов управления Windows Forms, <xref:System.Windows.Forms.Control>, предоставляет все необходимое для визуального отображения в клиентских приложений Windows. <xref:System.Windows.Forms.Control>предоставляет дескриптор окна, обработку маршрутизации сообщений и предоставляет интерфейс событий события клавиатуры и мыши, а также других пользователей. Он предоставляет дополнительный макет и имеет специальные свойства для визуального отображения, такие как <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>и многие другие. Кроме того он обеспечивает безопасность, поддержка и взаимодействие с элементами управления ActiveX работы с потоками. Поскольку существенная часть инфраструктуры предоставляется базовым классом, разрабатывать собственные элементы управления Windows Forms довольно просто.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Разработка простого элемента управления форм Windows Forms](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Разработка составного элемента Windows Forms](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
