---
title: Установка фона панели
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: ba2619354403793aea7ca15d43649da9637079a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744745"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Практическое руководство. Установка фона панели Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.Panel> может отображать как цвет фона, так и фоновое изображение. Свойство <xref:System.Windows.Forms.Control.BackColor%2A> задает цвет фона для вложенных элементов управления, таких как метки и переключатели. Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> не задано, выбор <xref:System.Windows.Forms.Control.BackColor%2A> будет заполнять всю панель. Если задано свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A>, изображение будет отображаться позади вложенных элементов управления.  
  
### <a name="to-set-the-background-programmatically"></a>Установка фонового рисунка программным способом  
  
1. Задайте для свойства <xref:System.Windows.Forms.Control.BackColor%2A> панели значение типа <xref:System.Drawing.Color?displayProperty=nameWithType>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Задайте свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> панели с помощью метода <xref:System.Drawing.Image.FromFile%2A> класса <xref:System.Drawing.Image?displayProperty=nameWithType>.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Элемент управления Panel](panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
