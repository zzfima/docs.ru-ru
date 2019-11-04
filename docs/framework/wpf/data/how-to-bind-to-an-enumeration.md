---
title: Практическое руководство. Привязка к перечислению
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454436"
---
# <a name="how-to-bind-to-an-enumeration"></a>Практическое руководство. Привязка к перечислению
В этом примере показано, как выполнить привязку к перечислению путем привязки к методу методов перечисления.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Controls.ListBox> отображает список значений перечисления <xref:System.Windows.HorizontalAlignment> с помощью привязки данных. <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Button> связаны так, что можно изменить значение свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.Controls.Button>, выбрав значение в <xref:System.Windows.Controls.ListBox>.  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>См. также

- [Создание привязки к методу](how-to-bind-to-a-method.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
