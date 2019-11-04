---
title: Практическое руководство. Очистка привязок
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 66f7eb0209d23660b9c7351ca793f509b2f4bb8d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458878"
---
# <a name="how-to-clear-bindings"></a>Практическое руководство. Очистка привязок
В этом примере показано, как удалять привязки к объекту.  
  
## <a name="example"></a>Пример  
 Чтобы удалить привязку из отдельного свойства объекта, вызовите <xref:System.Windows.Data.BindingOperations.ClearBinding%2A>, как показано в следующем примере. В следующем примере удаляется привязка из <xref:System.Windows.Controls.TextBlock.TextProperty> *myText*, объекта <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Очистка привязки удаляет привязку так, что значение свойства зависимостей изменяется на то значение, которое было бы без привязки. Это значение может быть значением по умолчанию, унаследованным или значением из привязки шаблона данных.  
  
 Чтобы очистить привязки от всех возможных свойств объекта, используйте <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.BindingOperations>
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
