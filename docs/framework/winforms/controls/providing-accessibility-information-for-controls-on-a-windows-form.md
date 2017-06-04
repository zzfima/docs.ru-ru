---
title: "Определение сведений, связанных со специальными возможностями, для элементов управления в Windows Forms | Microsoft Docs"
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
  - "Windows Forms — элементы управления, специальные возможности"
  - "элементы управления [Windows Forms], специальные возможности"
  - "специальные возможности, элементы управления Windows Forms"
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Определение сведений, связанных со специальными возможностями, для элементов управления в Windows Forms
Специальные возможности — это специализированные программы и устройства, помогающие людям с ограниченными возможностями эффективнее использовать компьютеры. Примеры: средства чтения с экрана для слепых и служебные программы голосового ввода для людей, использующих голосовые команды вместо мыши и клавиатуры. Специальные возможности взаимодействуют со свойствами специальных возможностей, представленными элементами управления Windows Forms. К этим свойствам относятся следующие.  
  
-   **AccessibilityObject**  
  
-   **AccessibleDefaultActionDescription**  
  
-   **AccessibleDescription**  
  
-   **AccessibleName**  
  
-   **AccessibleRole**  
  
## Свойство AccessibilityObject  
 Это свойство, доступное только для чтения, содержит экземпляр [класса AccessibleObject](frlrfSystemWindowsFormsAccessibleObjectClassTopic).**AccessibleObject** реализует интерфейс <xref:Accessibility.IAccessible>, предоставляющий описание элементов управления, расположение на экране, возможности навигации и значение. Конструктор задает это значение при добавлении элемента управления в форму.  
  
## Свойство AccessibleDefaultActionDescription  
 Эта строка описывает действие элемента управления. Она не отображается в окне "Свойства", и ее можно задать только в коде. В следующем примере это свойство задается для элемента управления "Кнопка".  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## Свойство AccessibleDescription  
 Эта строка описывает элемент управления. Его можно задать в окне "Свойства" или в коде следующим образом.  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## Свойство AccessibleName  
 Это имя элемента управления, переданное специальным возможностям. Его можно задать в окне "Свойства" или в коде следующим образом.  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## Свойство AccessibleRole  
 Это свойство, содержащее [перечисление AccessibleRole](frlrfSystemWindowsFormsAccessibleRoleClassTopic), описывает роль пользовательского интерфейса для элемента управления. Для нового элемента управления задано значение `Default`. Это означает, что по умолчанию элемент управления **Кнопка** работает как **Кнопка**. Возможно, потребуется сбросить это свойство, если у элемента управления есть другая роль. Например, вы можете использовать элемент управления **PictureBox** в качестве **Chart** и вам может потребоваться, чтобы специальные возможности передавали роль как **Chart**, а не как **PictureBox**. Возможно, вы захотите указать это свойство для разработанных пользовательских элементов управления. Это свойство можно задать в окне "Свойства" или в коде следующим образом.  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## См. также  
 <xref:System.Windows.Forms.AccessibleObject>   
 <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.AccessibleRole>