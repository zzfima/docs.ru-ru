---
title: "Советы по использованию элемента управления TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 802cc501b695f6c5cfe990bf72a4d9d2af68ba2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Советы по использованию элемента управления TableLayoutPanel
<xref:System.Windows.Forms.TableLayoutPanel> Управления предоставляет набор мощных функций, которые следует внимательно изучить перед использованием в Windows Forms.  
  
## <a name="recommendations"></a>Рекомендации  
 Следующие рекомендации помогут вам использовать <xref:System.Windows.Forms.TableLayoutPanel> управления ее преимущества.  
  
### <a name="targeted-use"></a>Целевое использование  
 Используйте <xref:System.Windows.Forms.TableLayoutPanel> управлять только в случае необходимости. Его не следует использовать во всех ситуациях, для создания макетов. В следующем списке описываются макеты, получить выгоду от использования <xref:System.Windows.Forms.TableLayoutPanel> управления:  
  
-   Макеты, в которых состоит из нескольких частей формы, пропорциональное изменение размеров друг с другом.  
  
-   Макеты, которые будут изменены или формируется динамически во время выполнения, например формы для ввода данных, имеющих настраиваемые поля, добавляется или вычитается на основе параметров.  
  
-   Макеты, которые должны оставаться в общую фиксированный размер. Например имеется диалоговым окном, которое должно остаться меньше, чем 800 x 600, но для поддержки локализованных строк.  
  
 В следующем списке описываются макеты, которые не выигрывают от использования значительно <xref:System.Windows.Forms.TableLayoutPanel> управления:  
  
-   Простые формы ввода данных с одним столбцом меток и один столбец областей ввода текста.  
  
-   Формы с одной большой областью отображения, которая должно заполнять все доступное пространство, при изменении размера. Примером этого является форма, отображающая один <xref:System.Windows.Forms.PropertyGrid> элемента управления. В этом случае используйте привязку, так как ничего должны расширяться при изменении размера формы.  
  
 Тщательно выбирать, какие элементы управления должны быть <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Если имеется достаточно места для увеличения на 30% с использованием привязки текста, рассмотрите возможность использования <xref:System.Windows.Forms.Control.Anchor%2A> только свойство. Если можно оценить пространство, необходимое для макета, использование <xref:System.Windows.Forms.Control.Dock%2A> и <xref:System.Windows.Forms.Control.Anchor%2A> проще, чем оценка сведения оставшегося пространства и <xref:System.Windows.Forms.Control.AutoSize%2A> поведение.  
  
 В целом при разработке макета с <xref:System.Windows.Forms.TableLayoutPanel> контроля, упрощения разработки.  
  
### <a name="use-the-document-outline-window"></a>Используйте окно структуры документа  
 Окно «Структура документа» дает древовидное представление макета, в котором можно использовать для работы с z порядка и иерархические связи элементов управления. Из **меню "Вид"**выберите **другие окна**, а затем выберите **Структура документа**.  
  
### <a name="avoid-nesting"></a>Старайтесь не использовать  
 Старайтесь не использовать другие <xref:System.Windows.Forms.TableLayoutPanel> управления внутри <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Отладка вложенных макетов может быть затруднено.  
  
### <a name="avoid-visual-inheritance"></a>Избегайте визуального наследования  
 <xref:System.Windows.Forms.TableLayoutPanel> Управления не поддерживает визуальное наследование в конструкторе Windows Forms. Объект <xref:System.Windows.Forms.TableLayoutPanel> элемент управления в производном классе, как «заблокирован» во время разработки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
