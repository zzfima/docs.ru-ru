---
title: "Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem | Microsoft Docs"
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
  - "отключение пунктов меню"
  - "пункты меню, отключение"
  - "пункты меню, включение"
  - "меню, отключение пунктов меню"
  - "ToolStripMenuItem - элементы, отключение"
  - "ToolStripMenuItem - элементы, включение"
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem
Можно ограничить или расширить набор команд, которые может выполнить пользователь, путем включения и отключения пунктов меню в ответ на действия пользователя.  При создании меню пункты меню включены по умолчанию, однако это можно изменить с помощью свойства <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>.  Изменить значение этого свойства можно в процессе разработки в окне **Свойства** или программным путем, добавив в код соответствующую настройку.  
  
### Чтобы отключить пункт меню программными средствами, выполните следующие действия:  
  
-   В методе, который использовался для задания свойств пункта меню, добавьте код для присвоения свойству <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> значения `false`.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  Отключение первого пункта меню или элемента верхнего уровня в меню приведет к скрытию всех пунктов меню, но не их отключению.  Аналогичным образом, отключение пункта меню, который имеет пункты вложенного меню, приведет к скрытию пунктов вложенного меню, но не их отключению.  Если пользователю становятся недоступны все команды конкретного меню, хорошим тоном считается отключать и скрывать меню целиком и предоставлять пользователю чистый интерфейс.  Обязательно нужно скрывать и отключать меню, а также отключать все пункты меню и пункты вложенного меню, потому что скрытие меню не запрещает доступ к командам меню с помощью сочетаний клавиш.  Чтобы скрыть меню полностью, установите для свойства <xref:System.Windows.Forms.ToolStripItem.Visible%2A> меню верхнего уровня значение `false`.  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Практическое руководство. Сокрытие объектов ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)