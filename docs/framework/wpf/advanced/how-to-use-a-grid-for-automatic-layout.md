---
title: "Практическое руководство. Использование сетки для автоматической разметки | Microsoft Docs"
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
  - "автоматический макет, использование сетки"
  - "сетки, автоматический макет"
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Использование сетки для автоматической разметки
В этот примере описаны способы использования сетки для автоматической разметки для создания локализуемого приложения.  
  
 Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени.  Часто при локализации необходимо изменять размеры и положение элементов в дополнение к переводу текста.  В прошлом каждый язык, на который переводился [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], требовал коррекции.  Теперь с возможностями среды [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разработать элементы, уменьшающие потребность в коррекции.  Подход к написанию приложений, в которых проще изменять размер и положение, называется `auto layout`.  
  
 В следующем примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] демонстрируется использование сетки для размещения нескольких кнопок и текста.  Обратите внимание на то, что для высоты и ширины ячейки установлено значение `Auto`; таким образом, ячейка, содержащая кнопку с изображением, выравнивается с этим изображением.  Так как элемент <xref:System.Windows.Controls.Grid> можно подогнать по его содержимому, он может быть полезен при использовании автоматического макета для создания локализуемых приложений.  
  
## Пример  
 В следующем примере показано использование сетки.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан вывод примера кода.  
  
 ![Пример сетки](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
Сетка  
  
## См. также  
 [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Использование автоматической разметки для создания кнопки](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)