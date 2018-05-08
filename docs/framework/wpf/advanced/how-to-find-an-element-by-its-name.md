---
title: Практическое руководство. Нахождение элемента по его имени
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: e2d176c9334c0a1d4c10819e0dc9f2c408e41d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-an-element-by-its-name"></a>Практическое руководство. Нахождение элемента по его имени
В этом примере описывается использование <xref:System.Windows.FrameworkElement.FindName%2A> метод, чтобы найти элемент по его <xref:System.Windows.FrameworkElement.Name%2A> значение.  
  
## <a name="example"></a>Пример  
 В этом примере обработчик событий кнопки представляет собой способ поиска определенного элемента по его имени. `stackPanel` — <xref:System.Windows.FrameworkElement.Name%2A> корневого <xref:System.Windows.FrameworkElement> которой выполняется поиск, и метод примере затем визуально указывает найденный элемент, приводя его <xref:System.Windows.Controls.TextBlock> и изменение одного из <xref:System.Windows.Controls.TextBlock> видимым [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] свойства.  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
