---
title: Практическое руководство. Использование автоматической разметки для создания кнопки
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 185bf71d4105d10a2bb85e6a0abd9da63c7d26f0
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185458"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Практическое руководство. Использование автоматической разметки для создания кнопки
В этом примере описывается, как использовать автоматическую разметку для создания кнопки в локализуемом приложении.  
  
 Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может занять много времени. Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов. В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился требовал коррекции. Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разрабатывать элементы, сокращающие потребность в коррекции. Подход к написанию приложений, в которых проще изменять размер и положение элементов, называется `automatic layout`.  
  
## <a name="example"></a>Пример  

Следующие два [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примеры создания приложений, позволяющих создать экземпляр кнопки: один с англоязычным текстом и один с текстом на испанском языке. Обратите внимание на то, что код является одинаковым, за исключением текста. Размер кнопки изменяется в соответствии с размером текста.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан результат выполнения примеров кода.  
  
 ![Та же кнопка с текстом на разных языках](./media/globalizationbutton.png "GlobalizationButton")  
Кнопка с автоматически изменяемым размером  
  
## <a name="see-also"></a>См. также

- [Обзор использования автоматической разметки](use-automatic-layout-overview.md)
- [Использование сетки для автоматической разметки](how-to-use-a-grid-for-automatic-layout.md)
