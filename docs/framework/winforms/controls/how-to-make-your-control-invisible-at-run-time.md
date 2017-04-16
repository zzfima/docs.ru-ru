---
title: "Практическое руководство. Сокрытие элемента управления во время выполнения | Microsoft Docs"
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
  - "элементы управления [Windows Forms], обеспечение невидимости во время выполнения"
  - "пользовательские элементы управления [Windows Forms], невидимые"
  - "невидимые элементы управления"
  - "время выполнения, обеспечение невидимости элементов управления"
  - "пользовательские элементы управления [Windows Forms], невидимые"
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Сокрытие элемента управления во время выполнения
В некоторых случаях требуется создать пользовательский элемент управления, который не должен быть виден во время выполнения.  Например, элемент управления, выполняющий функции будильника, должен отображаться только в момент звукового сигнала, оставаясь невидимым все остальное время.  Такой режим можно реализовать с помощью свойства <xref:System.Windows.Forms.Control.Visible%2A>.  Если свойство <xref:System.Windows.Forms.Control.Visible%2A> имеет значение `true`, элемент управления отображается как обычно.  Если свойство имеет значение `false`, элемент управления будет скрыт.  Несмотря на то, что при скрытии элемента управления его код все равно может выполняться, взаимодействие с элементом через пользовательский интерфейс становится невозможным.  Если требуется создать невидимый элемент управления, который реагирует на ввод данных пользователем \(например, на щелчок мышью\), следует создать прозрачный элемент управления.  Дополнительные сведения см. в разделе ["Задание прозрачного фона для элемента управления"](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).  
  
### Скрытие элемента управления во время выполнения  
  
1.  Установите для свойства <xref:System.Windows.Forms.Control.Visible%2A> значение `false`.  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Control.Visible%2A>   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Практическое руководство. Установка степени прозрачности фона элемента управления](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)