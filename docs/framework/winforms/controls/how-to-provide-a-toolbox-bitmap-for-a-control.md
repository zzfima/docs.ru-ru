---
title: "Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления | Microsoft Docs"
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
  - "растровые изображения [Windows Forms], пользовательские элементы управления"
  - "пользовательские элементы управления [Windows Forms], Растровые изображения панели элементов"
  - "Панель элементов [Windows Forms], добавление растровых изображений для пользовательских элементов управления"
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления
Если нужно, чтобы в **панели элементов** рядом с вашим элементом управления отображался особый значок, можно указать рисунок для этого с помощью класса <xref:System.Drawing.ToolboxBitmapAttribute>.  Этот класс представляет собой *атрибут* — особый тип класса, который можно присоединять к другим классам.  Дополнительные сведения о работе с атрибутами см. в разделах [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/ru-ru/0d0cff64-892d-4f57-83bd-bef388553d4f) для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] и [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md) для [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
 С помощью класса <xref:System.Drawing.ToolboxBitmapAttribute> можно задать строковое значение, которое указывает путь и имя файла, содержащего точечный рисунок размером 16 х 16 пикселей.  Этот рисунок появится рядом с элементом управления при добавлении элемента в **панель элементов**.  Можно также задать значение <xref:System.Type>. В этом случае загрузится рисунок, связанный с этим типом.  Если заданы оба значения, <xref:System.Type> и строковое значение, элемент управления будет искать файл рисунка с именем, заданным в строковом параметре, в сборке, которая содержит тип, заданный параметром <xref:System.Type>.  
  
### Чтобы задать для элемента управления точечный рисунок панели элементов  
  
1.  Добавьте в объявление класса элемента управления атрибут <xref:System.Drawing.ToolboxBitmapAttribute> перед ключевым словом `Class` для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] и над объявлением класса для [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  Постройте проект заново.  
  
    > [!NOTE]
    >  Растровый рисунок не будет отображаться в панели элементов для автоматически созданных элементов управления и компонентов.  Чтобы увидеть растровый рисунок, перезагрузите элемент управления с помощью окна **Выберите элементы панели элементов**.  Дополнительные сведения см. в разделе [Пример. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## См. также  
 <xref:System.Drawing.ToolboxBitmapAttribute>   
 [Пример. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [Создание элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Атрибуты](../Topic/Attributes%20\(Visual%20Basic\)1.md)   
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)