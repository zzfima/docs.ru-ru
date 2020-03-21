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
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182098"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Практическое руководство. Установка фона панели Windows Forms
Элемент управления <xref:System.Windows.Forms.Panel> Формами Windows может отображать как цвет фона, так и фоновое изображение. Свойство <xref:System.Windows.Forms.Control.BackColor%2A> устанавливает цвет фона для содержащихся элементов управления, таких как метки и радиокнопки. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не установлено, <xref:System.Windows.Forms.Control.BackColor%2A> выбор заполняет всю панель. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство установлено, изображение будет отображаться за содержащимися элементами управления.  
  
### <a name="to-set-the-background-programmatically"></a>Для программного набора фона  
  
1. Установите свойство <xref:System.Windows.Forms.Control.BackColor%2A> панели на значение <xref:System.Drawing.Color?displayProperty=nameWithType>типа.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Установите свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> панели <xref:System.Drawing.Image.FromFile%2A> методом <xref:System.Drawing.Image?displayProperty=nameWithType> класса.  
  
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
