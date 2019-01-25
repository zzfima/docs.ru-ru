---
title: Как выполнить Удаление всех декоративных элементов из элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 310b0249c215801b2634d51a1a1117bd7df83526
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680203"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Как выполнить Удаление всех декоративных элементов из элемента
В этом примере показано, как программным способом удаление всех декоративных элементов из указанного <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Пример  
 Этот подробный пример кода удаляет всех графических элементов в массиве декоративных элементов, возвращенных <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  В этом примере происходит с графические <xref:System.Windows.UIElement> с именем *myTextBox*.  Если этот элемент указан в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> нет графических объектов, `null` возвращается.  Этот код явно проверяет пустой массив и лучше всего подходит для приложений, где должен быть относительно распространенную пустой массив.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Пример  
 Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше. Этот код явно не проверяет пустой массив, так что вполне возможно, <xref:System.NullReferenceException> может быть вызвано исключение.  Этот код лучше всего подходит для приложений, где ожидается пустой массив довольно редки.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)
