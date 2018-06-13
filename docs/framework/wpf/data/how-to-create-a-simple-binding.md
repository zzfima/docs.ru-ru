---
title: Практическое руководство. Создать простой привязки
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 8910dd3ec6c9f72f9d8fb64cd33912f0d4318e5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555023"
---
# <a name="how-to-create-a-simple-binding"></a>Практическое руководство. Создать простой привязки
В этом примере показано, как создать простой <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется `Person` объект с строковое свойство с именем `PersonName`. `Person` Объект определен в пространстве имен `SDKSample`.  
  
 Выделенная строка, содержащий `<src>` элемент в следующем примере создается экземпляр `Person` объекта с `PersonName` значение свойства `Joe`. Это можно сделать в `Resources` статьи и назначены `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Выделенная строка, содержащий `<TextBlock>` привязывается элемент <xref:System.Windows.Controls.TextBlock> управления `PersonName` свойство. В результате <xref:System.Windows.Controls.TextBlock> имеет значение «Joe».  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
