---
title: "Практическое руководство. Размещение элементов управления в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4769d4c63c3cf87b6a2b640f3ab5a79b7cb30bf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-controls-on-windows-forms"></a>Практическое руководство. Размещение элементов управления в формах Windows Forms
Размещение элементов управления, использовать конструктор Windows Forms или задайте <xref:System.Windows.Forms.Control.Location%2A> свойство.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Чтобы разместить элемент управления в рабочей области конструирования в конструкторе Windows Forms  
  
-   Перетащите элемент управления в нужное место с помощью мыши.  
  
    > [!NOTE]
    >  Выберите элемент управления и переместите его со стрелкой клавиш со стрелками для более точного. Кроме того *линии привязки* поможет для точного размещения. Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Чтобы разместить элемент управления с помощью окна свойств  
  
1.  Щелкните элемент управления, который можно разместить.  
  
2.  В **свойства** окна, тип значения для <xref:System.Windows.Forms.Control.Location%2A> свойств, разделенных запятыми, чтобы разместить элемент управления внутри контейнера.  
  
     Первое число (X) представляет собой расстояние от левой границы контейнера; второе число (Y) представляет собой расстояние от верхней границы области контейнера, измеряется в пикселях.  
  
    > [!NOTE]
    >  Вы можете развернуть <xref:System.Windows.Forms.Control.Location%2A> свойство в тип **X** и **Y** отдельно.  
  
### <a name="to-position-a-control-programmatically"></a>Чтобы разместить элемент управления программными средствами  
  
1.  Задать <xref:System.Windows.Forms.Control.Location%2A> свойства элемента управления для <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Измените значение координаты X местоположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> вложенное свойство.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>Чтобы увеличить расположение элемента управления программными средствами  
  
1.  Задать <xref:System.Windows.Forms.Control.Left%2A> подчиненное координату X элемента управления.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Используйте <xref:System.Windows.Forms.Control.Location%2A> одновременно помещает свойства X и Y элемента управления. Чтобы задать положение по отдельности, используйте элемент управления <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) вложенное свойство. Не пытайтесь неявно задать координаты X и Y <xref:System.Drawing.Point> структуру, которая представляет расположение кнопки, потому что эта структура содержит копию координат кнопки.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Как: задать расположение экрана формы Windows Forms](http://msdn.microsoft.com/en-us/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
