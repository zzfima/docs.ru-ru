---
title: "Практическое руководство. Добавление обработки классов для перенаправленных событий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abbbdce0ca12c4d8bdd12f616bf49c3d6f66f441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Практическое руководство. Добавление обработки классов для перенаправленных событий
Перенаправленные события могут быть обработаны с помощью обработчики класса или экземпляров на любом узле данного маршрута. Обработчики класса вызываются первыми, а также может использоваться для подавления событий обработчиков экземпляров или введения вариантов поведения других событий для события, которые принадлежат базовых классов путем реализации класса. В этом примере показано два тесно связанные методы реализации обработчиков классов.  
  
## <a name="example"></a>Пример  
 В этом примере пользовательский класс на основе <xref:System.Windows.Controls.Canvas> панель. Основной замысел приложения состоит в том, что пользовательский класс представляет поведение его дочерних элементов, включая Перехват нажатия любой кнопок мыши и пометкой их обработать, прежде чем будет вызван класс дочернего элемента или обработчиков экземпляров на нем.  
  
 <xref:System.Windows.UIElement> Класс предоставляет виртуальный метод, который обеспечивает обработку класса <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> событие путем простого переопределения события. Это самый простой способ реализации обработки классов, если виртуальный метод доступен в любом месте иерархии класса. В следующем коде показано <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> реализацию в «MyEditContainer», который является производным от <xref:System.Windows.Controls.Canvas>. Реализация помечает событие как обработанное в аргументах и затем добавляет часть кода для предоставления исходному элементу основное видимое изменение.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Если нет виртуальных базовых классов или для этого конкретного метода, обработка класса можно добавить непосредственно с помощью служебной программы метод <xref:System.Windows.EventManager> класса <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Этот метод должен вызываться только внутри статической инициализации классов, которые используют обработку классов. В этом примере добавляется еще один обработчик для <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , и в этом случае зарегистрированный класс является пользовательским классом. Напротив, при использовании виртуальных методов, зарегистрированный класс является <xref:System.Windows.UIElement> базового класса. В случаях, где базовых классов и подклассов зарегистрировать обработку класса обработчики подклассов вызываются первыми. Поведение в приложении бы, что сначала этот обработчик отобразит окно сообщения, а затем будет показано визуальное изменение в обработчике виртуального метода.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.EventManager>  
 [Маркировка перенаправленных событий как обработанных и обработка классов](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Обработка перенаправленных событий](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
