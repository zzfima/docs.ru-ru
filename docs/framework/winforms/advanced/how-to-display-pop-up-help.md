---
title: "Практическое руководство. Отображение всплывающей справки | Microsoft Docs"
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
  - "Справка F1, в диалоговых окнах"
  - "формы, отображение справки"
  - "Справка, добавление в диалоговые окна"
  - "Справка, всплывающая справка"
  - "HelpProvider - компонент [Windows Forms]"
  - "модальные диалоговые окна, всплывающая справка"
  - "всплывающая справка"
  - "Windows Forms, отображение справки"
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Отображение всплывающей справки
Один из способов вывода справки в Windows Forms — нажатие кнопки **Справка**, которая находится в правой части строки заголовка, доступной через свойство <xref:System.Windows.Forms.Form.HelpButton%2A>.  Этот способ вывода справки хорошо подходит при работе с диалоговыми окнами.  Модальные диалоговые окна \(с методом <xref:System.Windows.Forms.Form.ShowDialog%2A>\) затрудняют работу внешних справочных систем, так как их нужно закрывать, чтобы перенести фокус на другое окно.  Кроме того, для использования кнопки **Справка** необходимо, чтобы в строке заголовка не было кнопок **Свернуть** и **Развернуть**.  При стандартном соглашении о структуре диалоговых окон в формах обычно есть кнопки **Свернуть** и **Развернуть**.  
  
 Следует помнить, что компонент <xref:System.Windows.Forms.HelpProvider> можно также использовать, чтобы связать элементы управления с файлами справочной системы, даже если применяется всплывающая справка.  Подробнее см. в разделе [Предоставление справки в приложении Windows](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.  Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Отображение всплывающей справки  
  
1.  Перетащите компонент [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) с панели элементов на форму.  
  
     Он разместится в нижней части конструктора Windows Forms.  
  
2.  В окне "Свойства" присвойте свойству <xref:System.Windows.Forms.Form.HelpButton%2A> значение `true`.  При этом в правой части строки заголовка формы появится кнопка с вопросительным знаком.  
  
3.  Для отображения <xref:System.Windows.Forms.Form.HelpButton%2A> свойствам <xref:System.Windows.Forms.Form.MinimizeBox%2A> и <xref:System.Windows.Forms.Form.MaximizeBox%2A> формы нужно присвоить значение `false`, свойству <xref:System.Windows.Forms.Form.ControlBox%2A> — значение `true`, а свойству <xref:System.Windows.Forms.Form.FormBorderStyle%2A> — одно из следующих значений: <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> или <xref:System.Windows.Forms.FormBorderStyle>.  
  
4.  Выберите элемент управления, для которого нужно отображать справку в форме, и укажите строку справки в окне "Свойства".  Это строка текста, которая будет отображаться в окне, аналогичном окну [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).  
  
5.  Нажмите клавишу **F5**.  
  
6.  Нажмите кнопку **Справка** в строке заголовка и щелкните элемент управления, для которого была задана строка справки.  
  
## См. также  
 [Отображение справки по элементам управления с помощью всплывающих подсказок](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Интеграция справки пользователя в формы Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)