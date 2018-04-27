---
title: Практическое руководство. Изменение границ в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 936d9d67454a272e79990f2e1b432391ecdc26a5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Практическое руководство. Изменение границ в Windows Forms
При определении внешнего вида и поведения формы Windows Forms можно выбрать из нескольких стилей границы. Изменив <xref:System.Windows.Forms.Form.FormBorderStyle%2A> свойство, можно управлять поведением изменения размеров формы. Кроме того, параметр <xref:System.Windows.Forms.Form.FormBorderStyle%2A> влияет на способ отображения строки заголовка и кнопок, которые на нем могут отображаться. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.FormBorderStyle>.  
  
 В Visual Studio предусмотрена расширенная поддержка данной задачи.  
  
 См. также [как: изменение границ формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Установка стиля границ формы Windows Forms программными средствами  
  
-   Задайте для свойства <xref:System.Windows.Forms.Form.FormBorderStyle%2A> нужный стиль. В следующем примере кода задает стиль границы формы `DlgBx1` для <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
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
  
     См. также [как: создание диалоговых окон во время разработки](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).  
  
     Кроме того Если выбран стиль границы для формы, которая предоставляет необязательный **свернуть** и **развернуть** кнопки, можно указать, хотите ли вы одной или обеих из этих кнопок, чтобы обеспечить работоспособность. Эти кнопки полезны в тех случаях, когда требуется точно управлять взаимодействием с пользователем. **Свернуть** и **развернуть** кнопки включены по умолчанию, и их функции изменяются с помощью **свойства** окна.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [Приступая к работе с Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
