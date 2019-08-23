---
title: Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: fdc52d0b94ce500b6560b60419d409f5cbd73b55
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932649"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a>Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 Этот раздел содержит пример кода, демонстрирующий, как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] использовать для вставки текста в однострочное текстовое поле. Альтернативный метод предоставляется для многострочных и многофункциональных элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] текстом, где неприменимо. Для сравнения в примере также демонстрируется использование методов Win32 для выполнения одинаковых результатов.  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется пошаговая последовательность элементов управления текстом в целевом приложении. Каждый элемент управления "текст" тестируется, <xref:System.Windows.Automation.ValuePattern> чтобы определить, можно ли получить объект из <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> него с помощью метода. Если элемент управления "текст" <xref:System.Windows.Automation.ValuePattern>поддерживает <xref:System.Windows.Automation.ValuePattern.SetValue%2A> , метод используется для вставки пользовательской строки в элемент управления Text. В противном случае используется метод.<xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a>См. также

- [Пример вставки текста TextPattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))
