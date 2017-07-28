---
title: "Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "Button - элемент управления [Windows Forms], назначение в качестве кнопки отмены"
  - "кнопки, кнопки отмены"
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора
В любой форме Windows Forms элемент управления <xref:System.Windows.Forms.Button> можно назначить кнопкой "Отмена".  Кнопка "Отмена" активируется при любом нажатии клавиши ESC, независимо от того, на каком элементе управления формы находится в этот момент фокус.  Такая кнопка обычно создается, чтобы позволить пользователю быстро прервать операцию, не выполняя никакого действия.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы назначить кнопку "Отмена"  
  
1.  Выберите форму, в которой находится кнопка.  
  
2.  В окне **Свойства** установите значение свойства формы <xref:System.Windows.Forms.Form.CancelButton%2A> равным имени элемента управления <xref:System.Windows.Forms.Button>.  
  
## См. также  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)