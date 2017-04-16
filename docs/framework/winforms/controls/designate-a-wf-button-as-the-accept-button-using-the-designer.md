---
title: "Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "Accept - кнопка в формах Windows Forms"
  - "Button - элемент управления [Windows Forms], назначение по умолчанию"
  - "кнопки, значения по умолчанию в Windows Forms"
  - "элементы управления Windows Forms, кнопка по умолчанию в форме"
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора
В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button> кнопкой "Принять", называемой также кнопкой по умолчанию.  Кнопка по умолчанию нажимается при любом нажатии клавиши ВВОД независимо от того, на каком элементе управления формы в этот момент находится фокус.  Исключение составляют случаи, когда элемент управления, на котором находится фокус, является другой кнопкой \(в этом случае нажимается кнопка, на которой находится фокус\), многострочным текстовым полем или настраиваемым элементом управления, перехватывающими клавишу ВВОД.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы назначить кнопку "Принять"  
  
1.  Выберите форму, в которой находится кнопка.  
  
2.  В окне **Свойства** задайте в качестве свойства формы <xref:System.Windows.Forms.Form.AcceptButton%2A> имя элемента управления <xref:System.Windows.Forms.Button>.  
  
## См. также  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>   
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)