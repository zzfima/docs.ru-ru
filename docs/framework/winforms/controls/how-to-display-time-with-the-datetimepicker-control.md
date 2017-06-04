---
title: "Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker | Microsoft Docs"
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
  - "DateTimePicker - элемент управления [Windows Forms], отображение времени"
  - "примеры [Windows Forms], DateTimePicker - элемент управления"
  - "время, отображение в элементе управления DateTimePicker"
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker
Чтобы пользователи приложения могли выбирать дату и время, которые будут отображаться в указанном формате, используйте элемент управления <xref:System.Windows.Forms.DateTimePicker>.  Ниже показано, как использовать элемент управления <xref:System.Windows.Forms.DateTimePicker> для отображения времени.  
  
### Отображение времени с помощью элемента управления DateTimePicker  
  
1.  Задайте свойству <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение <xref:System.Windows.Forms.DateTimePickerFormat>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2.  Присвойте свойству <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> элемента <xref:System.Windows.Forms.DateTimePicker> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## Пример  
 В примере кода ниже показано, как создать элемент <xref:System.Windows.Forms.DateTimePicker>, позволяющий пользователю выбирать только время.  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 [Элемент управления DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)