---
title: "Обработка введенных пользователем данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "пользовательские элементы управления [Windows Forms], события клавиатуры, использующие код"
  - "пользовательские элементы управления [Windows Forms], события мыши, использующие код"
  - "пользовательские элементы управления [Windows Forms], ввод данных пользователем с использованием кода"
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Обработка введенных пользователем данных
В этом разделе описываются основные события клавиатуры и мыши, предоставляемые элементом управления <xref:System.Windows.Forms.Control?displayProperty=fullName>.  При обработке события необходимо переопределить защищенный метод `On`*ИмяСобытия* вместо подключения делегата к событию.  Список событий см. в разделе [Raising Events from a Component](../Topic/Raising%20Events%20from%20a%20Component.md).  
  
> [!NOTE]
>  При отсутствии данных, связанных с событием, в качестве аргумента для метода `On`*ИмяСобытия* передается экземпляр базового класса <xref:System.EventArgs>.  
  
## События клавиатуры  
 Основными событиями клавиатуры, которые может обрабатывать элемент управления пользователя, являются <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress> и <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Имя события|Переопределяемый метод|Описание события|  
|-----------------|----------------------------|----------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Создается только при первоначальном нажатии клавиши.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Создается при каждом нажатии клавиши.  Если клавиша удерживается нажатой, событие <xref:System.Windows.Forms.Control.KeyPress> создается через повторяющийся интервал времени, определенный операционной системой.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Создается, когда клавиша отпускается.|  
  
> [!NOTE]
>  Обработка ввода с клавиатуры значительно сложнее, чем переопределение событий в предыдущей таблице, и ее описание выходит за границы этого раздела.  Дополнительные сведения см. в разделе [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).  
  
## События мыши  
 Основные события мыши, обрабатываемые элементом управления — <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove> и <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Имя события|Переопределяемый метод|Описание события|  
|-----------------|----------------------------|----------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Создается при нажатии кнопки мыши в тот момент, когда указатель находится над элементом управления.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Создается, когда указатель первый раз входит в область элемента управления.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Создается, когда указатель находится над элементом управления.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Создается, когда указатель покидает область элемента управления.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Создается, когда указатель перемещается в области элемента управления.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Создается при отпускании кнопки мыши, когда указатель находится над элементом управления или покидает область элемента управления.|  
  
 Следующий фрагмент кода показывает пример переопределения события <xref:System.Windows.Forms.Control.MouseDown>.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Следующий фрагмент кода показывает пример переопределения события <xref:System.Windows.Forms.Control.MouseMove>.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Следующий фрагмент кода показывает пример переопределения события <xref:System.Windows.Forms.Control.MouseUp>.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Полный исходный код для примера `FlashTrackBar` содержится в разделе [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## См. также  
 [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Определение событий](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [События](../../../../docs/standard/events/index.md)   
 [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)