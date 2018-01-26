---
title: "Практическое руководство. Использование сетки для автоматической разметки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbd8bd7e36b7b773837b839e77ec88a8e7c8f0d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Практическое руководство. Использование сетки для автоматической разметки
В этот примере описаны способы использования сетки для автоматической разметки с целью создания локализуемого приложения.  
  
 Локализация [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] может быть много времени. Часто при локализации, помимо перевода текста, необходимо изменять размеры и положение элементов. В прошлом каждый язык, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] переводился необходимые корректировки. Теперь с возможностями [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] можно разработать элементы, которые снижают потребность в коррекции. Подход к написанию приложений, которые могут быть легко изменять размер и положение называется `auto layout`.  
  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере демонстрируется использование сетки для размещения нескольких кнопок и текста. Обратите внимание, что высоты и ширины ячейки установлено значение `Auto`; поэтому ячейку, содержащую кнопку с изображением изменяется, чтобы вместить изображение. Поскольку <xref:System.Windows.Controls.Grid> элемент можно скорректировать, чтобы его содержимое может быть полезно при использовании подхода автоматический макет для разработки приложений, которые могут быть локализованы.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано использование сетки.  
  
 [!code-xaml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 На приведенном ниже рисунке показан результат выполнения примера кода.  
  
 ![Пример сетки](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob_grid")  
Grid  
  
## <a name="see-also"></a>См. также  
 [Обзор использования автоматической разметки](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Использование автоматической разметки для создания кнопки](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)
