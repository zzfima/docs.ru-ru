---
title: "Практическое руководство. Использование автоматической разметки для создания кнопки | Microsoft Docs"
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
  - "автоматический макет, создание кнопок"
  - "элементы управления "Кнопка", создание с автоматическим макетом"
  - "создание, кнопок с автоматическим макетом"
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Использование автоматической разметки для создания кнопки
В данном примере описано, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.  
  
 Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени.  Часто при локализации необходимо изменять размеры и положение элементов в дополнение к переводу текста.  В прошлом каждый язык, на который переводился [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], требовал коррекции.  Теперь с возможностями среды [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разработать элементы, уменьшающие потребность в коррекции.  Подход к написанию приложений, в которых легче изменять размер и положение, называется `automatic layout`.  
  
 В следующих двух примерах [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] создаются приложения, которые создают экземпляр кнопки. Один пример с текстом на английском языке, а другой с текстом на испанском языке.  Обратите внимание, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.  
  
## Пример  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан вывод примеров кода.  
  
 ![Та же кнопка с текстовой подписью на различных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
## См. также  
 [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Использование сетки для автоматической разметки](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)