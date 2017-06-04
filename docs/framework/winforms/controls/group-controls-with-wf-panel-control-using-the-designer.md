---
title: "Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "элементы управления [Windows Forms], группирование"
  - "Panel - элемент управления [Windows Forms], группирование элементов управления"
  - "элементы управления Windows Forms, группирование"
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора
Элементы управления Windows Forms <xref:System.Windows.Forms.Panel> используются для группировки других элементов управления.  Существуют три причины для группировки элементов управления.  Первая — визуальная группировка связанных элементов форм для упрощения пользовательского интерфейса; вторая — программная группировка, например, переключателей; третья — перемещение элементов управления как единого целого в режиме разработки.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать группу элементов управления, выполните следующие действия:  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.Panel> из вкладки **Windows Forms** панели элементов в форму.  
  
2.  Добавьте другие элементы управления в панель путем рисования каждого элемента внутри панели.  
  
     Если требуется включить в панель уже существующие элементы управления, можно выделить все элементы управления, вырезать их в буфер обмена, выбрать элемент управления <xref:System.Windows.Forms.Panel> и затем вставить их в панель.  Можно также перетащить их в панель.  
  
3.  \(Необязательно\) Добавление границы на панель производится путем задания для нее значения свойства <xref:System.Windows.Forms.BorderStyle>.  Имеются три варианта выбора: <xref:System.Windows.Forms.BorderStyle>, <xref:System.Windows.Forms.BorderStyle> и <xref:System.Windows.Forms.BorderStyle>.  
  
## См. также  
 [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Практическое руководство. Задание фона панели](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)