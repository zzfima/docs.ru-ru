---
title: Практическое руководство. Обеспечение доступности данных для привязки в XAML
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174190"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Практическое руководство. Обеспечение доступности данных для привязки в XAML
Эта тема обсуждает различные способы, которыми можно сделать данные доступными для связывания в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]зависимости от потребностей приложения.  
  
## <a name="example"></a>Пример  
 Если у вас есть общий язык времени выполнения (CLR) объект, который вы хотели бы привязать к от [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], `x:Key`один из способов вы можете сделать объект доступным для связывания, чтобы определить его как ресурс и дать ему . В следующем примере у `Person` вас есть объект `PersonName`с именем свойства строки. Объект `Person` (в строке, показанной, `<src>` которая содержит элемент) определяется в подзванном `SDKSample`пространстве имен.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Затем можно связать <xref:System.Windows.Controls.TextBlock> элемент управления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]с объектом в, как `<TextBlock>` показано выделенной строке, содержащей элемент.
  
 Кроме того, вы <xref:System.Windows.Data.ObjectDataProvider> можете использовать класс, как в следующем примере:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Связывание определяется таким же образом, как `<TextBlock>` показано на выделенной строке, содержащей элемент.  
  
 В данном конкретном примере результат тот <xref:System.Windows.Controls.TextBlock> же: у `Joe`вас есть с текстовым контентом. Тем не <xref:System.Windows.Data.ObjectDataProvider> менее, класс предоставляет такие функциональные возможности, как возможность привязываться к результату метода. Вы можете использовать <xref:System.Windows.Data.ObjectDataProvider> класс, если вам нужна функция, которая она предоставляет.  
  
 Однако, если вы привязываетесь к объекту, `DataContext` который уже создан, необходимо установить код, как в следующем примере.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Чтобы получить доступ к данным <xref:System.Windows.Data.XmlDataProvider> XML для связывания с помощью класса, см. [Привязка к данным XML С помощью XMLDataProvider и XPath-запросов.](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md) Для доступа к данным XML для связывания с <xref:System.Windows.Data.ObjectDataProvider> помощью класса см. [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
  
 Для получения информации о многих способах указания связываемых данных [см.](how-to-specify-the-binding-source.md) Для получения информации о том, какие типы данных можно связывать или как реализовать объекты общего времени выполнения языка (CLR) для связывания, [см.](binding-sources-overview.md)  
  
## <a name="see-also"></a>См. также раздел

- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Как-к темам](data-binding-how-to-topics.md)
