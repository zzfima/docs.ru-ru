---
title: Изменить границы формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739567"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Практическое руководство. Изменение границ в Windows Forms
При определении внешнего вида и поведения формы Windows Forms можно выбрать из нескольких стилей границы. Изменив <xref:System.Windows.Forms.Form.FormBorderStyle%2A> свойство, можно управлять поведением изменения размеров формы. Кроме того, параметр <xref:System.Windows.Forms.Form.FormBorderStyle%2A> влияет на способ отображения строки заголовка и кнопок, которые на нем могут отображаться. Для получения дополнительной информации см. <xref:System.Windows.Forms.FormBorderStyle>.  
  
 В Visual Studio предусмотрена расширенная поддержка данной задачи.  
  
 См. также [руководство. изменение границ Windows Forms с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Установка стиля границ формы Windows Forms программными средствами  
  
- Задайте для свойства <xref:System.Windows.Forms.Form.FormBorderStyle%2A> нужный стиль. В следующем примере кода задается стиль границы формы `DlgBx1` для <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     См. также [руководство. Создание диалоговых окон во время разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).  
  
     Кроме того, если вы выбрали стиль границы для формы, которая предоставляет необязательные кнопки **сворачивания** и **развертывания** , можно указать, должна ли работать одна или обе эти кнопки. Эти кнопки полезны в тех случаях, когда требуется точно управлять взаимодействием с пользователем. Кнопки **сворачивания** и **развернуть** включены по умолчанию, и их функциональность управляется в окне **Свойства** .  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [Приступая к работе с Windows Forms](getting-started-with-windows-forms.md)
