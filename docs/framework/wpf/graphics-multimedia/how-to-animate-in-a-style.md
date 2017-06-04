---
title: "Практическое руководство. Применение анимации в стиле | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, свойства, в стилях"
  - "стили, анимация свойств в"
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Применение анимации в стиле
В этом примере показано, как анимировать свойства в стиле.  Если анимация используется внутри стиля, то можно обратиться только к тем элементам структуры, для которых определен стиль.  Чтобы обратиться к фиксируемому объекту, необходимо «поставить точку» из свойства элемента со стилем.  
  
 В следующем примере несколько анимаций определены в стиле и применены к объекту <xref:System.Windows.Controls.Button>.  Когда пользователь помещает указатель мыши над кнопкой, ее прозрачность изменяется до полупрозрачности и обратно.  Когда пользователь удаляет указатель мыши с кнопки, она становится полностью непрозрачной.  При нажатии кнопки цвет ее фона меняется с оранжевого на белый и обратно.  Поскольку объект <xref:System.Windows.Media.SolidColorBrush> используется для рисования, кнопка не может быть выбрана напрямую, доступ к ней осуществляется через свойство кнопки <xref:System.Windows.Controls.Control.Background%2A>.  
  
## Пример  
 [!code-xml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Обратите внимание, что при анимации с использованием стиля можно выбрать не существующий объект.  Например, предположим, что стиль использует объект <xref:System.Windows.Media.SolidColorBrush> для задания свойства фона кнопки, но в некоторый момент стиль переопределяется и фон кнопки устанавливается с помощью объекта <xref:System.Windows.Media.LinearGradientBrush>.  При попытке анимации объекта <xref:System.Windows.Media.SolidColorBrush> не создается исключение; анимация просто не будет выполнена.  
  
 Дополнительные сведения о синтаксисе планирования раскадровки см. в разделе [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).