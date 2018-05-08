---
title: Рисование и отрисовка пользовательского элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 18a05a739f42d41a650e66723f44aae69c1707c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="custom-control-painting-and-rendering"></a>Рисование и отрисовка пользовательского элемента управления
Пользовательское рисование элементов управления является одним из сложных задач, стало проще платформой .NET Framework. При создании пользовательского элемента управления, существует несколько вариантов относительно графического внешнего вида элемента управления. При создании элемента управления, который наследует от `Control`, необходимо предоставить код, позволяющий элементу управления выполнить визуализацию графического представления. При создании пользовательского элемента управления путем наследования от `UserControl`, или при наследовании от одного из элементов управления Windows Forms, может переопределить стандартное графическое представление и предоставить собственный код графики. Если вы хотите предоставить пользовательскую отрисовку для составных элементов управления `UserControl` при разработке, параметров становится более ограниченным, но по-прежнему можно воспользоваться широкими графическими возможностями для элементов управления и приложений.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Отрисовка элементов управления Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 Показано, как запрограммировать логику отображения элемента управления.  
  
 [Элементы управления, разработанные пользователем](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 Обзор действий, необходимых для записи и переопределения код отрисовки для элемента управления.  
  
 [Составные элементы управления](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 Описывает, как реализовать пользовательский код отрисовки для составных элементов управления в пользовательских элементах управления и формах.  
  
 [Практическое руководство. Скрытие элемента управления во время выполнения](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 Показано, как использовать <xref:System.Windows.Forms.Control.Visible%2A> свойство, чтобы скрыть или отобразить элемент управления.  
  
 [Практическое руководство. Установка степени прозрачности фона элемента управления](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 Показано, как использовать <xref:System.Windows.Forms.Control.SetStyle%2A> метод для создания цвет фона, который является непрозрачным, прозрачным или полупрозрачным.  
  
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 Показано, как отображать элементы управления с использованием стилей оформления в операционных системах, которые их поддерживают.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Control>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
 <xref:System.Windows.Forms.UserControl>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Описание этого метода.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Представляет [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] функциональных возможностей графики из Visual Studio и ссылки на дополнительные сведения.  
  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 Описание типов пользовательских элементов управления, которые можно создать.
