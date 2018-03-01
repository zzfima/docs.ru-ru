---
title: "Практическое руководство. Изменение границ в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e977617f16ef882ad0dcfe1a96a6e8af73d2ae48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Практическое руководство. Изменение границ в Windows Forms
При определении внешнего вида и поведения формы Windows Forms можно выбрать из нескольких стилей границы. Изменив <xref:System.Windows.Forms.Form.FormBorderStyle%2A> свойство, можно управлять поведением изменения размеров формы. Кроме того, параметр <xref:System.Windows.Forms.Form.FormBorderStyle%2A> влияет на способ отображения строки заголовка и кнопок, которые на нем могут отображаться. Для получения дополнительной информации см. <xref:System.Windows.Forms.FormBorderStyle>.  
  
 В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] предусмотрена расширенная поддержка этой задачи.  
  
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
