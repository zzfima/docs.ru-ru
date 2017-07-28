---
title: "How to: Change the Borders of Windows Forms | Microsoft Docs"
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
  - "Windows Forms, changing the borders"
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Change the Borders of Windows Forms
При определении внешнего вида и поведения формы Windows Forms можно выбрать из нескольких стилей границы.  Изменив <xref:System.Windows.Forms.Form.FormBorderStyle%2A> свойство, можно управлять поведением изменения размеров формы.  Кроме того, параметр <xref:System.Windows.Forms.Form.FormBorderStyle%2A> влияет на способ отображения строки заголовка и кнопок, которые на нем могут отображаться.  Для получения дополнительной информации см. <xref:System.Windows.Forms.FormBorderStyle>.  
  
 В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] предусмотрена расширенная поддержка этой задачи.  
  
 См. также [Практическое руководство. Изменение границ формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).  
  
### Установка стиля границ формы Windows Forms программными средствами  
  
-   Задайте для свойства <xref:System.Windows.Forms.Form.FormBorderStyle%2A> нужный стиль.  Следующий пример кода задает стиль границы формы`DlgBx1` в <xref:System.Windows.Forms.FormBorderStyle>.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     См. также [Практическое руководство. Создание диалоговых окон во время разработки.](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).  
  
     Кроме того, если выбран стиль границы для формы, для которого кнопки **Свернуть** и **Развернуть** необязательны, то можно указать, требуются ли функционирование обеих или одной из этих кнопок.  Эти кнопки полезны в тех случаях, когда требуется точно управлять взаимодействием с пользователем.  Кнопки **Свернуть** и **Развернуть** включены по умолчанию и их функции изменяются с помощью окна **Свойства**.  
  
## См. также  
 <xref:System.Windows.Forms.FormBorderStyle>   
 <xref:System.Windows.Forms.FormBorderStyle>   
 [Getting Started with Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)