---
title: "Практическое руководство. Создание кнопки, содержащей изображение | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Button - элементы управления [WPF], создание"
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание кнопки, содержащей изображение
В этом примере показано, как включить изображение в объект <xref:System.Windows.Controls.Button>.  
  
## Пример  
 В следующем примере демонстрируется создание двух элементов управления <xref:System.Windows.Controls.Button>.  Один элемент управления <xref:System.Windows.Controls.Button> — содержит текст, а другой — изображение.  Изображение находится в папке data, которая вложена в папку проекта этого примера.  Когда пользователь щелкает объект <xref:System.Windows.Controls.Button>, который содержит изображение, изменяется фон и текст другого объекта <xref:System.Windows.Controls.Button>.  
  
 В этом примере элементы управления <xref:System.Windows.Controls.Button> создаются с помощью разметки, но для создания обработчиков событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> используется код.  
  
 [!code-xml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## См. также  
 [Элементы управления](../../../../docs/framework/wpf/controls/index.md)   
 [Библиотека элементов управления](../../../../docs/framework/wpf/controls/control-library.md)