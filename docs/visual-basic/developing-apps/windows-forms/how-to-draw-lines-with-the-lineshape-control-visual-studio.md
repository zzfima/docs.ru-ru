---
title: "Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "линии, рисование"
  - "LineShape - элемент управления"
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Изображение линий при помощи элемента управления LineShape (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.LineShape> для изображения горизонтальных, вертикальных или диагональных линий в форме или контейнере, и во время выполнения, и на этапе разработки.  
  
 **Примечание** На компьютере могут отображаться разные имена или расположения некоторых элементов пользовательского интерфейса Visual Studio, отличающиеся от указанных в дальнейших инструкциях.  Эти элементы определяются используемым выпуском Visual Studio и его параметрами.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы нарисовать линию на этапе разработки  
  
1.  Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.LineShape> из вкладки **Visual Basic PowerPacks** в **панели элементов** на форму или контейнерный элемент управления.  
  
2.  Измените размер и приведите обработчики к размеру и расположению линии.  
  
     Можно также изменить размер и расположение линии, изменив свойства `X1`, `X2`, `Y1` и `Y2` в окне **Свойства**.  
  
3.  В окно **Свойства**, можно добавить такие дополнительные свойства, как `BorderStyle` или `BorderColor`, чтобы изменить внешний вид линии.  
  
### Чтобы нарисовать линию во время выполнения  
  
1.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
2.  В диалоговом окне **Добавить ссылку**, выберите **Microsoft.VisualBasic.PowerPacks.VS**, и затем нажмите **OK**.  
  
3.  В **Редакторе кода** добавьте оператор `Imports` или `using`в начало модуля:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
4.  В процедуру `Event` добавьте следующий код:  
  
     [!code-cs[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>   
 [Знакомство с элементами управления Line и Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)   
 [Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)