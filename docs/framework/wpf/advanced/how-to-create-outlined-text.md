---
title: "Практическое руководство. Вывод текста по контуру | Microsoft Docs"
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
  - "градиентная кисть"
  - "кисть с линейным градиентом"
  - "контурный текст"
  - "оформление, кисть с линейным градиентом"
  - "оформление, контурные эффекты"
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Вывод текста по контуру
В большинстве случаев при добавлении декоративных элементов в текстовые строки в приложении [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] используется текст в виде коллекции дискретных символов или глифов.  Например, можно создать кисть линейного градиента и применить ее к свойству <xref:System.Windows.Controls.Control.Foreground%2A> объекта <xref:System.Windows.Controls.TextBox>.  Когда происходит отображение или редактирование текстового поля, кисть линейного градиента автоматически применяется к текущему набору символов в строке текста.  
  
 ![Текст, отображенный при помощи кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext01.png "OutlinedText01")  
Пример кисти линейного градиента, применяемой к текстовому полю  
  
 В то же время текст можно также преобразовать в объекты <xref:System.Windows.Media.Geometry>, что позволяет создавать другие типы визуально насыщенного текста.  Например, можно создать объект <xref:System.Windows.Media.Geometry>, основанный на контуре строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
Пример кисти линейного градиента, применяемой к геометрической форме контура текста  
  
 Текст, преобразованный в объект <xref:System.Windows.Media.Geometry>, не является набором символов, для которого изменение символов в текстовой строке невозможно.  Тем не менее, внешний вид преобразованного текста можно изменять с помощью свойств штриха и заливки.  Штрих — это контур преобразованного текста, а заливка — область внутри контура преобразованного текста.  
  
 Следующие примеры демонстрируют несколько способов создания визуальных эффектов, изменяя штрих и заливку преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
Пример установки разного цвета для штриха и заливки  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
Пример применения кисти к штриху  
  
 Также возможно изменить прямоугольник ограничивающего поля или выделить преобразованный текст.  Следующий пример демонстрирует способ создания визуальных эффектов путем изменения штриха и выделения преобразованного текста.  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Пример применения кисти к штриху и выделению  
  
## Пример  
 Чтобы преобразовать текст в объект <xref:System.Windows.Media.Geometry>, необходимо использовать объект <xref:System.Windows.Media.FormattedText>.  После создания этого объекта можно использовать методы <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> и <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> для преобразования текста в объекты <xref:System.Windows.Media.Geometry>.  Первый метод возвращает геометрическую форму форматированного текста, а второй — геометрическую форму ограничивающего поля форматированного текста.  В следующем примере показано создание объекта <xref:System.Windows.Media.FormattedText> и извлечение геометрических форм форматированного текста и его ограничивающего поля.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Чтобы отобразить извлеченные объекты <xref:System.Windows.Media.Geometry>, необходимо иметь доступ к <xref:System.Windows.Media.DrawingContext> объекта, который отображает преобразованный текст.  В приведенных примерах кода это делается путем создания объекта пользовательского элемента управления, который является производным от класса, поддерживающего определенную пользователем отрисовку.  
  
 Чтобы отобразить объекты <xref:System.Windows.Media.Geometry> в пользовательском элементе управления, выполните переопределение для метода <xref:System.Windows.UIElement.OnRender%2A>.  Переопределенный метод должен использовать метод <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> для рисования объектов <xref:System.Windows.Media.Geometry>.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## См. также  
 [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)