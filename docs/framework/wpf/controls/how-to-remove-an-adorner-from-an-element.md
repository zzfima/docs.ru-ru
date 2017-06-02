---
title: "Практическое руководство. Удаление объекта класса Adorner из элемента | Microsoft Docs"
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
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Удаление объекта класса Adorner из элемента
В данном примере показано, как программными средствами удалить определенный декоративный элемент из указанного объекта <xref:System.Windows.UIElement>.  
  
## Пример  
 Этот подробный пример кода удаляет первый декоративный элемент из массива декоративных элементов, возвращаемого методом <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  В данном примере графические объекты получаются в <xref:System.Windows.UIElement>, который называется *myTextBox*.  Если у элемента, указанного в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>, нет графических объектов, возвращается `null`.  Этот код явно проверяет пустой массив и наилучшим образом подходит для приложений, где пустой массив может возникать относительно часто.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## Пример  
 Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше.  Этот код не проверяет явно пустой массив, поэтому возможно возникновение исключения <xref:System.NullReferenceException>.  Этот код наилучшим образом подходит для приложений, где пустой массив возникает редко.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)