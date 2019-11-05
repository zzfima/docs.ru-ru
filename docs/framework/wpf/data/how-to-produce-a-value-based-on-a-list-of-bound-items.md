---
title: Практическое руководство. Создание значений на основе списка связанных элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459692"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Практическое руководство. Создание значений на основе списка связанных элементов
<xref:System.Windows.Data.MultiBinding> позволяет привязать свойство целевого объекта привязки к списку свойств источника, а затем применить логику для получения значения с заданными входными данными. В этом примере показано, как использовать <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Пример  
 В следующем примере `NameListData` ссылается на коллекцию объектов `PersonName`, которые являются объектами, содержащими два свойства, `firstName` и `lastName`. В следующем примере создается <xref:System.Windows.Controls.TextBlock>, где сначала отображаются имя и фамилия человека с фамилией.  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Чтобы понять, как получается формат фамилии-имени, рассмотрим реализацию `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 Класс `NameConverter` реализует интерфейс списка <xref:System.Windows.Data.IMultiValueConverter>. `NameConverter` принимает значения от отдельных привязок и сохраняет их в массиве объектов значений. Порядок, в котором элементы <xref:System.Windows.Data.Binding> отображаются под элементом <xref:System.Windows.Data.MultiBinding>, — это порядок, в котором эти значения хранятся в массиве. На значение атрибута <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> ссылается аргумент Parameter метода <xref:System.Windows.Data.MultiBinding.Converter%2A>, который выполняет параметр в параметре, чтобы определить способ форматирования имени.  
  
## <a name="see-also"></a>См. также

- [Преобразование привязанных данных](how-to-convert-bound-data.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
