---
title: Практическое руководство. сделать объект Freezable доступным только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460069"
---
# <a name="how-to-make-a-freezable-read-only"></a>Практическое руководство. сделать объект Freezable доступным только для чтения
В этом примере показано, как сделать <xref:System.Windows.Freezable> только для чтения, вызвав его метод <xref:System.Windows.Freezable.Freeze%2A>.  
  
 Нельзя зафиксировать объект <xref:System.Windows.Freezable>, если одно из следующих условий `true` об объекте:  
  
- Он имеет анимированные или привязанные к данным свойства.  
  
- Он имеет свойства, заданные динамическим ресурсом. Дополнительные сведения о динамических ресурсах см. в разделе [ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Он содержит <xref:System.Windows.Freezable> подобъекты, которые не могут быть заморожены.  
  
 Если эти условия `false` для объекта <xref:System.Windows.Freezable> и вы не собираетесь его изменять, попробуйте заморозить его, чтобы получить выигрыш в производительности.  
  
## <a name="example"></a>Пример  
 В следующем примере закрепляется <xref:System.Windows.Media.SolidColorBrush>, который является типом объекта <xref:System.Windows.Freezable>.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Дополнительные сведения о <xref:System.Windows.Freezable> объектах см. в разделе [Общие сведения об объектах Freezable](freezable-objects-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Общие сведения об объектах класса Freezable](freezable-objects-overview.md)
- [Разделы практического руководства](base-elements-how-to-topics.md)
