---
title: Изменение внешнего вида компонента ColorDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746636"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms
Внешний вид компонента Windows Forms <xref:System.Windows.Forms.ColorDialog> можно настроить с помощью ряда свойств. Диалоговое окно содержит два раздела — один, который показывает основные цвета и один, позволяющий пользователю определять пользовательские цвета.  
  
 Большая часть свойств ограничивает выбор цветов, которые пользователь может выбрать в диалоговом окне. Если свойство <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> имеет значение `true`, пользователю разрешено определять пользовательские цвета. Свойство <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> `true`, если диалоговое окно развернуто для определения пользовательских цветов. в противном случае пользователь должен нажать кнопку "определить пользовательский цвет". Если свойство <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> имеет значение `true`, в диалоговом окне отображаются все доступные цвета в наборе основных цветов. Если свойство <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> имеет значение `true`, пользователь не может выбрать другие цвета. для выбора доступны только сплошные цвета.  
  
 Если свойство <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> имеет значение `true`, в диалоговом окне появляется кнопка Справка. Когда пользователь нажимает кнопку "Справка", возникает событие <xref:System.Windows.Forms.CommonDialog.HelpRequest> компонента <xref:System.Windows.Forms.ColorDialog>.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>Настройка внешнего вида диалогового окна «цвет»  
  
1. Задайте нужные значения свойств <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>и <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ColorDialog>
- [Компонент ColorDialog](colordialog-component-windows-forms.md)
- [Общие сведения о компоненте ColorDialog](colordialog-component-overview-windows-forms.md)
