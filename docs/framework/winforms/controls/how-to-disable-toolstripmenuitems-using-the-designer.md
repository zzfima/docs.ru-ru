---
title: "Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора | Microsoft Docs"
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
  - "пункты меню, отключение"
  - "меню, отключение элементов"
  - "MenuStrip - элемент управления [Windows Forms], отключение элементов меню в конструкторе"
  - "ToolStripMenuItem - элементы, отключение в конструкторе"
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора
Можно ограничить или расширить набор команд, которые может выполнить пользователь, путем включения и отключения пунктов меню в ответ на действия пользователя.  При создании меню пункты меню включены по умолчанию, однако это можно изменить с помощью свойства <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>.  Изменить значение этого свойства можно в процессе разработки в окне **Свойства** или программным путем, добавив в код соответствующую настройку.  Дополнительные сведения см. в разделе [Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы отключить пункт меню в процессе разработки, выполните следующие действия:  
  
1.  Выберите в форме пункт меню и установите для свойства <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> значение `false`.  
  
    > [!TIP]
    >  Отключение первого пункта меню или элемента верхнего уровня в меню приведет к отключению всех пунктов меню.  Аналогичным образом, отключение пункта меню, который имеет вложенное меню, приведет к отключению пунктов вложенного меню.  Если пользователю становятся недоступны все команды конкретного меню, хорошим тоном считается отключать и скрывать меню целиком и предоставлять пользователю чистый интерфейс.  Обязательно нужно скрывать и отключать меню, потому что скрытие меню не запрещает доступ к командам меню с помощью сочетаний клавиш.  Чтобы скрыть меню полностью, установите для свойства <xref:System.Windows.Forms.ToolStripItem.Visible%2A> меню верхнего уровня значение `false`.  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Практическое руководство. Сокрытие объектов ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)