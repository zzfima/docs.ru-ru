---
title: "Практическое руководство. Создание значений на основе списка связанных элементов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d16a198ed78c1ffd9dcaad595e9cc9be3cb2de0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Практическое руководство. Создание значений на основе списка связанных элементов
<xref:System.Windows.Data.MultiBinding>можно привязать к целевому свойству привязки к списку свойств источника и затем применить логику для получения значения с заданными входными данными. В этом примере демонстрируется использование <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Пример  
 В следующем примере `NameListData` ссылается на коллекцию объектов `PersonName`, которые являются объектами, содержащими два свойства, `firstName` и `lastName`. В следующем примере создается <xref:System.Windows.Controls.TextBlock> , показаны имена и фамилии лица с фамилией первой.  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Чтобы понять, как получается формат фамилии-имени, рассмотрим реализацию `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 Класс `NameConverter` реализует интерфейс списка <xref:System.Windows.Data.IMultiValueConverter>. `NameConverter` принимает значения от отдельных привязок и сохраняет их в массиве объектов значений. Порядок, в котором <xref:System.Windows.Data.Binding> элементы отображаются в списке <xref:System.Windows.Data.MultiBinding> соответствует порядку, в котором эти значения хранятся в массиве. Значение <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> атрибут ссылается аргумент параметра <xref:System.Windows.Data.MultiBinding.Converter%2A> метод, который переключается на параметр, чтобы определить способ форматирования имени.  
  
## <a name="see-also"></a>См. также  
 [Преобразование привязанных данных](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
