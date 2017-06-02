---
title: "Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms | Microsoft Docs"
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
  - "элементы управления [Windows Forms], создание"
  - "элементы управления [Windows Forms], отслеживание процесса"
  - "FlashTrackBar - пользовательский элемент управления"
  - "ход выполнения, отчеты [Windows Forms"
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms
В следующем примере кода показан пользовательский элемент управления с именем `FlashTrackBar`, который можно использовать для отображения пользователю уровня или хода выполнения приложения.  Он использует градиент для визуального представления хода выполнения.  
  
 Элемент управления `FlashTrackBar` иллюстрирует следующие понятия.  
  
-   Определение пользовательских свойств.  
  
-   Определение пользовательских событий.  \(`FlashTrackBar` определяет событие `ValueChanged`.\)  
  
-   Переопределение метода <xref:System.Windows.Forms.Control.OnPaint%2A> для предоставления логики для рисования элемента управления.  
  
-   Расчет области, доступной для рисования элемента управления, используя его свойство <xref:System.Windows.Forms.Control.ClientRectangle%2A>.  `FlashTrackBar` выполняет это в своем методе `OptimizedInvalidate`.  
  
-   Реализация сериализации \(устойчивости\) для свойства, когда оно изменяется в конструкторе Windows Forms.  `FlashTrackBar` определяет методы `ShouldSerializeStartColor` и `ShouldSerializeEndColor` для сериализации своих свойств `StartColor` и `EndColor`.  
  
 В следующей таблице указаны настраиваемые свойства, которые определяет `FlashTrackBar`.  
  
|Свойство.|Описание|  
|---------------|--------------|  
|`AllowUserEdit`|Показывает, может ли пользователь изменять значение бегунка, отслеживающего текущее положение, с помощью щелчка или перетаскивания.|  
|`EndColor`|Задает конечный цвет бегунка.|  
|`DarkenBy`|Задает, насколько темен фон по отношению к градиенту переднего плана.|  
|`Max`|Задает максимальное значение бегунка.|  
|`Min`|Задает минимальное значение бегунка.|  
|`StartColor`|Задает начальный цвет градиента.|  
|`ShowPercentage`|Указывает, отображать ли знак процентов над градиентом.|  
|`ShowValue`|Указывает, отображать ли текущее значение над градиентом.|  
|`ShowGradient`|Указывает, должен ли бегунок отображать градиент цвета, показывая текущее значение.|  
|-   `Value`|Задает текущее значение бегунка.|  
  
 В следующей таблице указаны дополнительные члены, определяемые событием измененного свойства `FlashTrackBar:` и методом, инициирующим событие.  
  
|Элемент|Описание|  
|-------------|--------------|  
|`ValueChanged`|Событие, инициированное при изменении свойства бегунка `Value`.|  
|`OnValueChanged`|Метод, инициирующий событие `ValueChanged`.|  
  
> [!NOTE]
>  `FlashTrackBar` использует класс <xref:System.EventArgs> для данных события, и <xref:System.EventHandler> – для делегата события.  
  
 Для обработки соответствующих событий *EventName*, `FlashTrackBar` переопределяет следующие методы, наследуемые им от <xref:System.Windows.Forms.Control?displayProperty=fullName>:  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 Для обработки соответствующих событий изменения свойств `FlashTrackBar` переопределяет следующие методы, наследуемые им от <xref:System.Windows.Forms.Control?displayProperty=fullName>:  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## Пример  
 Элемент управления `FlashTrackBar` определяет два редактора типов пользовательских интерфейсов, `FlashTrackBarValueEditor` и `FlashTrackBarDarkenByEditor`, указанные в следующем листинге кода.  Класс `HostApp` использует элемент управления `FlashTrackBar` в Windows Form.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## См. также  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Основы разработки элементов управления форм Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)