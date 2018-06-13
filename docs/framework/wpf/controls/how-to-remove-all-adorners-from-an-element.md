---
title: Практическое руководство. Удаление всех декоративных элементов из элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 5b7e2038c8a314a180ba097a30c124f874c25893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551620"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Практическое руководство. Удаление всех декоративных элементов из элемента
В этом примере показано, как программно удалить все графические элементы из указанного <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Пример  
 Этот подробный пример кода удаляет все графические элементы в массив декоративных элементов, возвращенных <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  В этом примере происходит с графические <xref:System.Windows.UIElement> с именем *myTextBox*.  Если у элемента, указанного в вызове <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> нет графических объектов, `null` возвращается.  Этот код явно проверяет пустой массив и наилучшим образом подходит для приложений, где пустой массив должен быть относительно часто.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Пример  
 Данный сжатый пример кода функционально эквивалентен подробному примеру, приведенному выше. Этот код не проверяет явно пустой массив, поэтому возможно, <xref:System.NullReferenceException> может быть вызвано исключение.  Этот код является наилучшим образом подходит для приложений, где пустой массив, ожидается редко.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md)
