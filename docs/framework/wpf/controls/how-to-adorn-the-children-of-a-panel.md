---
title: Практическое руководство. Декорирование дочерних элементов Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923517"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Практическое руководство. Декорирование дочерних элементов Panel
В этом примере показано, как программно привязать декоративный элемент к дочерним элементам указанного <xref:System.Windows.Controls.Panel>объекта.  
  
## <a name="example"></a>Пример  
 Чтобы привязать декоративный элемент к дочерним <xref:System.Windows.Controls.Panel>элементам, выполните следующие действия.  
  
1. Объявите новый <xref:System.Windows.Documents.AdornerLayer> объект и `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> вызовите метод, чтобы найти слой декоративных элементов для элемента, чьи дочерние элементы должны быть декоративными.  
  
2. Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента к каждому дочернему элементу.  
  
 В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> именованного *мистаккпанел*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о декоративных элементах](adorners-overview.md)
