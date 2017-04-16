---
title: "Практическое руководство. Добавление обработки классов для перенаправленных событий | Microsoft Docs"
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
  - "обработчики классов, перенаправляемые события"
  - "перенаправляемые события, обработчики классов"
  - "перенаправляемое событие области задач с обработкой класса"
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Добавление обработки классов для перенаправленных событий
Перенаправленные события могут быть обработаны с помощью обработчиков классов или экземпляров на любом узле данного маршрута.  Обработчики классов вызываются первыми и могут использоваться классами реализации для подавления событий обработчиков экземпляров или введения новых вариантов поведения для событий, которые относятся к базовым классам.  В этом примере иллюстрируются два тесно связанных между собой способа реализации обработчиков классов.  
  
## Пример  
 В этом примере пользовательский класс основан на панели <xref:System.Windows.Controls.Canvas>.  Основным условием для работы приложения является то, что пользовательский класс представляет поведение его дочерних элементов, включая перехват нажатия любых кнопок мыши и пометкой его как обработанного, перед тем как на нем будет вызван какой\-либо обработчик экземпляров или класс дочернего элемента.  
  
 Класс <xref:System.Windows.UIElement> предоставляет виртуальный метод, позволяющий классу обрабатывать событие <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> путем простого переопределения события.  Это наиболее простой способ реализации обработки классов, если такой виртуальный метод доступен где\-либо в иерархии класса.  В следующем коде показана реализация <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> в «MyEditContainer», который является производным от <xref:System.Windows.Controls.Canvas>.  Реализация помечает событие как обработанное в аргументах и затем добавляет часть кода для предоставления исходному элементу основное видимое изменение.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Если нет доступного виртуального метода для базовых классов или для этого конкретного метода, обработка классов может добавляться напрямую с помощью служебного метода класса <xref:System.Windows.EventManager>, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.  Этот метод следует вызывать только внутри статической инициализации классов, которые используют обработку классов.  В этом примере добавляется еще один обработчик для <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>, и в этом случае зарегистрированный класс является пользовательским классом.  В свою очередь, при использовании виртуальных методов зарегистрированный класс является базовым классом <xref:System.Windows.UIElement>.  В случаях, когда и базовые классы, и подклассы регистрируют обработку классов, обработчики подклассов вызываются первыми.  Сначала этот обработчик отобразит окно сообщения, а затем будет показано визуальное изменение в обработчике виртуального метода.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## См. также  
 <xref:System.Windows.EventManager>   
 [Маркировка перенаправленных событий как обработанных и обработка классов](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Обработка перенаправленных событий](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)