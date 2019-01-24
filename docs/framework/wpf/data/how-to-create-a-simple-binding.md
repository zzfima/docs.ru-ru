---
title: Как выполнить Создание простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 3e38fa5fd1c7d0a635efd93de6ebe551f1eb1b82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594841"
---
# <a name="how-to-create-a-simple-binding"></a>Как выполнить Создание простой привязки
В этом примере показано, как создать простое <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`. `Person` Объект определен в пространстве имен `SDKSample`.  
  
 Выделенная строка, содержащий `<src>` элемента в следующем примере создается экземпляр `Person` со `PersonName` значение свойства `Joe`. Это можно сделать в `Resources` раздела и назначенный `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Выделенная строка, содержащий `<TextBlock>` затем привязывает элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство. В результате <xref:System.Windows.Controls.TextBlock> отображается со значением «Joe».  
  
## <a name="see-also"></a>См. также
- [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
