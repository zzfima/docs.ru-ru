---
title: Практическое руководство. Добавление данных пользователя в данные рукописного ввода
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 40d883f3d3e1d504c8757c31325aa72a03da37e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544515"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Практическое руководство. Добавление данных пользователя в данные рукописного ввода
Можно добавлять пользовательские данные для рукописного ввода, которая будет сохранена при сохранении рукописный ввод как рукописный ввод сериализованного формата (ISF).  Можно сохранить пользовательские данные для <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, или <xref:System.Windows.Ink.Stroke>.  Возможность сохранить пользовательские данные в трех объектов дает возможность выбрать лучшее место для сохранения данных.  Все три класса используют аналогичные методы для хранения и доступа к пользовательским данным.  
  
 Только следующие типы могут сохраняться как пользовательские данные:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>[]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>[]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>[]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>[]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>[]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>[]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>[]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>[]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>[]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>[]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>[]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>[]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>[]  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует добавление и извлечение пользовательских данных из <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 В следующем примере создается приложение, которое отображает <xref:System.Windows.Controls.InkCanvas> и две кнопки.  Кнопка, `switchAuthor`, позволяет использовать два разных авторах два пера.  Кнопки `changePenColors` изменяет цвет каждого штриха на <xref:System.Windows.Controls.InkCanvas> согласно автору.  Приложение определяет два <xref:System.Windows.Ink.DrawingAttributes> объектов и добавляет пользовательское свойство для каждого из них, указывающее, какой автор, перетащенной <xref:System.Windows.Ink.Stroke>.  Когда пользователь щелкает `changePenColors`, приложение изменяет внешний вид штриха согласно значению пользовательского свойства.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
