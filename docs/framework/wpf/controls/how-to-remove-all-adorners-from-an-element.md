---
title: "Практическое руководство. Удаление всех декоративных элементов из элемента | Microsoft Docs"
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
  - "декоративные элементы, удаление"
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Удаление всех декоративных элементов из элемента
В этом примере демонстрируется программное удаление всех графических объектов из указанного <xref:System.Windows.UIElement>.  
  
## Пример  
 В этом подробном примере кода удаляются все графические объекты из массива графических объектов, возвращенного методом <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  В данном примере графические объекты получаются в <xref:System.Windows.UIElement>, который называется *myTextBox*.  Если у элемента, указанного в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>, нет графических объектов, возвращается `null`.  Этот код явно проверяет пустой массив и наилучшим образом подходит для приложений, где пустой массив может возникать относительно часто.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## Пример  
 Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше.  Этот код не проверяет явно пустой массив, поэтому возможно возникновение исключения <xref:System.NullReferenceException>.  Этот код наилучшим образом подходит для приложений, где пустой массив возникает редко.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)