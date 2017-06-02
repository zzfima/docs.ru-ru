---
title: "Практическое руководство. Привязка графического элемента к элементу | Microsoft Docs"
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
  - "декоративные элементы, привязка к указанным элементам UIElement"
  - "UIElements, привязка декоративных элементов"
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Привязка графического элемента к элементу
В этом примере описывается порядок программной привязки графического элемента к заданному объекту <xref:System.Windows.UIElement>.  
  
## Пример  
 Для привязки графического элемента к конкретному объекту <xref:System.Windows.UIElement> выполните следующие действия:  
  
1.  Вызовите статический \(`static`\) метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>, чтобы получить объект <xref:System.Windows.Documents.AdornerLayer> для оформляемого объекта <xref:System.Windows.UIElement>.  Метод <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> перемещается вверх по визуальному дереву, начиная с заданного **элемента пользовательского интерфейса**, и возвращает первый найденный слой графических элементов.  \(Если уровни графических элементов не найдены, метод возвращает значение null.\)  
  
2.  Вызовите метод <xref:System.Windows.Documents.AdornerLayer.Add%2A> для привязки графического элемента к нужному объекту **UIElement**.  
  
 В следующем примере выполняется привязка объекта SimpleCircleAdorner \(см. выше\) к объекту <xref:System.Windows.Controls.TextBox> с именем *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки элемента оформления к другому элементу в текущей версии не поддерживается.  
  
## См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)