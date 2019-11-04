---
title: Практическое руководство. Создать простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453512"
---
# <a name="how-to-create-a-simple-binding"></a>Практическое руководство. Создать простой привязки
В этом примере показано, как создать простой <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется объект `Person` со строковым свойством с именем `PersonName`. Объект `Person` определен в пространстве имен с именем `SDKSample`.  
  
 Выделенная строка, содержащая элемент `<src>` в следующем примере, создает объект `Person` со значением свойства `PersonName` `Joe`. Это делается в разделе `Resources` и назначается `x:Key`.  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Выделенная строка, содержащая элемент `<TextBlock>`, привязывает элемент управления <xref:System.Windows.Controls.TextBlock> к свойству `PersonName`. В результате <xref:System.Windows.Controls.TextBlock> отображается со значением Joe.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
