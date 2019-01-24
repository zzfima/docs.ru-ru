---
title: Как выполнить Использование автоматической разметки для создания кнопки
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 501341f0e71e6e5a224c51e4ae01c68ce6b845cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543491"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Как выполнить Использование автоматической разметки для создания кнопки
В этом примере описывается, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.  
  
 Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени. Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов. В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился требовал коррекции. Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разрабатывать элементы, сокращающие потребность в коррекции. Подход к написанию приложений, в которых проще изменять размер и положение элементов, называется `automatic layout`.  
  
 Следующие два [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры создания приложений, позволяющих создать экземпляр кнопки: один с англоязычным текстом и один с текстом на испанском языке. Обратите внимание на то, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.  
  
## <a name="example"></a>Пример  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан результат выполнения примеров кода.  
  
 ![Та же кнопка с текстом на разных языках](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
## <a name="see-also"></a>См. также
- [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
- [Использование сетки для автоматической разметки](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
