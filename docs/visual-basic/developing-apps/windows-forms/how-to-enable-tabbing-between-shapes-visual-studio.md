---
title: "Пошаговое руководство. Разрешение переходов между фигурами (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line - элемент управления, реализация переходов"
  - "Shape - элемент управления, реализация переходов"
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Пошаговое руководство. Разрешение переходов между фигурами (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

У элементов управления Line и shape нет свойств `TabStop` или `TabIndex`, но сохраняется возможность включить переход между ними.  В следующем примере одновременное нажатие CTRL и TAB приведет к переключению между фигурами; нажатие только TAB приведет к переключению между кнопками.  
  
> [!NOTE]
>  Отображаемые на компьютере имена или расположения некоторых элементов пользовательского интерфейса Visual Studio могут отличаться от указанных в следующих инструкциях.  Эти элементы определяются используемым выпуском Visual Studio и его параметрами.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы разрешить переключение между фигурами  
  
1.  Перетащите три элемента управления <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> и два элемента управления <xref:System.Windows.Forms.Button> из панели **Панель элементов** на форму.  
  
2.  В **Редакторе кода** добавьте оператор `Imports` или `using`в начало модуля:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
3.  В процедуру обработки события добавьте следующий код:  
  
     [!code-cs[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  В процедуру обработки события `Button1_PreviewKeyDown` добавьте следующий код:  
  
     [!code-cs[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## См. также  
 [Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [Пошаговое руководство. Изображение линий при помощи элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Знакомство с элементами управления Line и Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)