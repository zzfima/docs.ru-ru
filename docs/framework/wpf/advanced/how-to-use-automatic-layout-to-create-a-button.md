---
title: "Практическое руководство. Использование автоматической разметки для создания кнопки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d55dc1330c21e7eb9f7cfd7f554234dccd6f274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Практическое руководство. Использование автоматической разметки для создания кнопки
В этом примере описывается, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.  
  
 Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может быть много времени. Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов. В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился необходимые корректировки. Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разработать элементы, которые снижают потребность в коррекции. Подход к написанию приложений, которые могут быть легко изменять размер и положение называется `automatic layout`.  
  
 Ниже приведены два [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры создания приложений, позволяющих создать экземпляр кнопки; с англоязычным текстом и полноразмерных испанский текст. Обратите внимание на то, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.  
  
## <a name="example"></a>Пример  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан результат выполнения примеров кода.  
  
 ![Та же кнопка с текстовой подписью на различных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
## <a name="see-also"></a>См. также  
 [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Использование сетки для автоматической разметки](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
