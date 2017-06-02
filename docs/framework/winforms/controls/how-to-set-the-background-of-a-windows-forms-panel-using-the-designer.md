---
title: "Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "цвета фона, элементы управления панели [Windows Forms]"
  - "фоновые изображения, элементы управления панели [Windows Forms]"
  - "цвета, элементы управления панели [Windows Forms]"
  - "Panel - элемент управления [Windows Forms], фон"
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора
Элемент управления Windows Forms <xref:System.Windows.Forms.Panel> может отображать как цвет фона, так и фоновое изображение.  Свойство <xref:System.Windows.Forms.Control.BackColor%2A> задает цвет фона для элементов управления, представленных на панели, таких как метки и переключатели.  Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> не задано, выбранный фрагмент <xref:System.Windows.Forms.Control.BackColor%2A> заполняет панель полностью.  Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> задано, за отображаемыми на панели элементами управления отображается указанное изображение.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.Panel>.  Сведения о настройке такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы задать фон в конструкторе Windows Forms  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.Panel>.  
  
2.  В окне **Свойства** нажмите кнопку со стрелкой рядом со свойством <xref:System.Windows.Forms.Control.BackColor%2A> для отображения окна с тремя вкладками.  
  
3.  Выберите вкладку **Настраиваемый** для отображения цветовой палитры.  
  
4.  Перейдите на вкладку **Веб** или **Система** для отображения списка предопределенных имен цветов, а затем выберите цвет.  
  
5.  В окне **Свойства** щелкните стрелку рядом со свойством <xref:System.Windows.Forms.Control.BackgroundImage%2A>.  
  
6.  В диалоговом окне **Открыть** выберите файл, который следует отобразить.  
  
## См. также  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)